# sdlc-check task

## Description:

The sdlc-check task is a very simple test that tests if the built product is following all RH-SDLC (Secure Development lifecycle) practices.

The task will simply look for the associated Jira trackers and will print a warning if all tasks are not closed. If you have any problem understanding what this means, please speak with your assigned Security Engineer (SE). He will help you to be compliant with Red Hat security practices.

To obtain the `JIRA_EPIC_KEY` speak with your assigned Security Engineer

## Params:

| name          | description                                   |
|---------------|-----------------------------------------------|
| JIRA_EPIC_KEY | Jira Key for the feature in SDLC Jira project |
| JIRA_TOKEN    | JIRA Personal Access Token (PAT)              |


