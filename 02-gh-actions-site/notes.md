## Changes made:
1. originally used test.yml to upload and test actions

2. Changed yml action file name
- changed name to deploy project
- added second job


## Notes
### Parallel jobs vs sequential
- parallel jobs requires the 'needs' keyword to make one job wait for another to finish
- sequential jobs run one after the other by default
- added 'needs: build' to deploy job to make it wait for build job to finish

- ways to test make sequential jobs:
  - use 'needs' keyword
  - set up separate workflows for each job
  - use manual triggers to control job execution order
- added comments to yml file for clarity

3. Adding second events trigger
- added 'workflow_dispatch' to allow manual triggering of workflow
Deploy Project (in GitHub Actions UI) > Run workflow button

4. Expressiona and GH context
- used expressions to dynamically set job parameters based on context
- used github context to access info about the workflow run, repo, etc.
- example: set job name based on branch name or commit message
- example: use github.event_name to conditionally run steps based on event type
