#!/usr/bin/env groovy
 
/**
 * Sample Jenkinsfile for Jenkins2 Pipeline
 * from https://github.com/hotwilson/jenkins2/edit/master/Jenkinsfile
 * by wilsonmar@gmail.com 
 * edited by: Cole
 */
// this is a comment
import hudson.model.*
import hudson.EnvVars
import groovy.json.JsonSlurperClassic
import groovy.json.JsonBuilder
import groovy.json.JsonOutput
import java.net.URL
 
try {
    node {
        stage '\u2776 Stage 1 - Property Output'
        
        echo "\u2600 SOURCE_BRANCH=${env.BRANCH_NAME}"
        
        echo "\u2600 BUILD_URL=${env.BUILD_URL}"
        
        echo "\u2600 BUILD_NUMBER=${env.BUILD_NUMBER}"
 
        def workspace = pwd()
        echo "\u2600 workspace=${workspace}"
 
        stage '\u2777 Stage 2 - Verify and Build'

        // if branch name == 'master'
        // do whatever is required for master branch
        //if branch name like 'feature%'
        // do whatever is required for feature branches -> build/verify
        // if branch name like 'dev'
        //do build tests -> deploy to development env
        // if branch name like 'QA'
        // do build tests -> deploy to QA -> update JIRA ticket to closed (through GitHub)
        // if branch name like 'hotfix'
        // do build instructions

        if (env.BRANCH_NAME == 'develop' ) {
            println "In Development Branch"
        }
    } // node
} // try end
catch (exc) {
    /*
     err = caughtError
     currentBuild.result = "FAILURE"
     String recipient = 'infra@lists.jenkins-ci.org'
     mail subject: "${env.JOB_NAME} (${env.BUILD_NUMBER}) failed",
             body: "It appears that ${env.BUILD_URL} is failing, somebody should do something about that",
               to: recipient,
          replyTo: recipient,
     from: 'noreply@ci.jenkins.io'
    */
} finally {
  
 //(currentBuild.result != "ABORTED") && node("master") {
     // Send e-mail notifications for failed or unstable builds.
     // currentBuild.result must be non-null for this step to work.
     //step([$class: 'Mailer',
     //   notifyEveryUnstableBuild: true,
     //   recipients: "${email_to}",
     //   sendToIndividuals: true])
    println 'Some finally step'
//}
 
 // Must re-throw exception to propagate error:
    if (err) {
        throw err
    }
}
