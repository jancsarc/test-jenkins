#!/usr/bin/env groovy
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

stage '\u2776 Stage 1 - Branch Environment'

def gitURL = "https://github.com/jancsarc/test-jenkins.git"
def command = "git ls-remote -h $gitURL"

def proc = command.execute()
proc.waitFor()              

if ( proc.exitValue() != 0 ) {
   println "Error, ${proc.err.text}"
   System.exit(-1)
}

def branches = proc.in.text.readLines().collect { 
    it.replaceAll(/[a-z0-9]*\trefs\/heads\//, '') 
}

return branches
