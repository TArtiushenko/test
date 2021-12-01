## Github actions settings

secrets:
 - GCP_PROJECT  
 - GCP_SERVICE_ACCOUNT_KEY  
 - GCP_DEPLOY_SERVICE_ACCOUNT_KEY  
 - SLACK_WEBHOOK  

env:  
 - GCP_ZONE - zone name fot registry  
 - IMAGE - prefered image name  
 - REPOSITORY - artifact registry repository name  
 - CLUSTER_NAME  
 - CLUSTER_ZONE  


triggers:  
 - push to dev  
 - pull request to release, main branches  
 - push tag with rc- and v prefixes  

 push to dev makes dev-{timestamp} tag for image, deploys to dev namespace  
 pull request to release makes rc-{increment} tag for image also creates same github tag, deploys to stage namespace  
 pull request to main makes v{increment} tag for image also creates same github tag, deploys to prod namespace  

images are pushed to google container registry or artifact registry (commented out)  

slack messages on build and deploy to prod  
 
 flux added