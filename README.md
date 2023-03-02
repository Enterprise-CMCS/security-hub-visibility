# Security Hub Visibility

## A GitHub action that syncs Security Hub findings with Jira issues


1. gets all current findings from Security Hub, filtered by the `Severity` of the findings (default is `CRITICAL,HIGH,MEDIUM`)

2. creates Jira issues for findings that do not already have a Jira issue
    - each Security Hub Finding type (by title) is represented as a single issue, e.g. if there are three resources that have violated the 'S3.8' rule there will be a single S3.8 Jira issue created

3. closes existing Jira issues in the target project if their underlying findings are longer active


Please see `action.yml` for required and optional inputs, and `test.yml` for an example of how to use this action.

This action is backed by the `macpro-security-hub-sync` NPM package.  See https://github.com/Enterprise-CMCS/macpro-security-hub-sync for details.

