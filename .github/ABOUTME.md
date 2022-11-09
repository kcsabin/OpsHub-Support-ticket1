# Templates and GitHub Actions used for the automation
## Issue Templates
* Utilizes Github [Issue Templates](https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/configuring-issue-templates-for-your-repository) under `.github/ISSUE_TEMPLATE/*template.md` to define issue types `Epic`, `User Story`, `Bugs`, `Feature Request`, `Service Request`. 

## Labels
* https://github.com/crazy-max/ghaction-github-labeler --> Manage labels as code using `labels.yml`. Product labels, Squads, and work item labels are included: `DM`, `DBaaS`, `Squad1`, `Squad2`, `Epic`, `User Story`, `Points: 3`, etc.

## Actions
* https://github.com/alex-page/github-project-automation-plus --> Use issue webhooks to add or transition issues (project cards) to their respective Product Kanban board.

## TO DO
* https://github.com/philschatz/project-bot --> This would have been a better solution but couldn't get this app to work (last commit was 2 years ago). By using this you wouldn't need Github Actions and the added overhead of each repo having this action file, instead we could configure this GitHub App to listen to all or select repositories without the need to expose Github PAT token anywhere. Possibly fork this repo and update to fix.

* https://github.com/marketplace/actions/vault-secrets --> Use Vault Secrets instead of GitHub Secrets to store our credentials for this project.