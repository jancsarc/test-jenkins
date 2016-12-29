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

println env.BRANCH_NAME
println {env.BRANCH_NAME}
println env.JOB_NAME.replaceFirst('.+/', '')
${env.BRANCH_NAME}
