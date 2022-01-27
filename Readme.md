## Github actions settings

secrets:
 - GCP_PROJECT
 - GCP_SERVICE_ACCOUNT_KEY
 - SLACK_WEBHOOK

env:
 - GCP_ZONE - zone name
 - IMAGE - prefered image name
 - REPOSITORY - artifact registry repository name


triggers:
 - push to dev
 - pull request to release, main branches
 - push tag with rc- and v prefixes

 push to dev makes dev-{timestamp} tag for image  
 pull request to release makes rc-{increment} tag for image also creates same github tag  
 pull request to main makes v{increment} tag for image also creates same github tag  

 outdated

test j
