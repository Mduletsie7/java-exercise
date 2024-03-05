Exercise:
.github/workflows directory: This will contain the main workflow file (main.yml) that triggers the others.
 
Separate YAML files: build.yml: This file will define the build steps for the application. deploy.yml: This file will reference an external script and handle deployment to Azure App Services.
 
External script: Create for bash script containing the logic for deploying the application.
 
Workflow Breakdown:
main.yml: This file will be the main entry point for the workflow. Use the on keyword to define the trigger (e.g., push to main branch). Use the jobs keyword to define multiple jobs within the workflow. In each job, use the uses keyword to reference the separate YAML files (build.yml and deploy.yml). build.yml: This file will contain the build steps specific to your chosen programming language. Use actions like actions/checkout to get the code, language-specific build actions.
 
deploy.yml: This file will reference the external script for deployment. Use the uses keyword with a relative path to the script. Optionally, you can pass arguments to the script if needed for deployment configuration. External Script (pipeline.sh): This script will contain the logic for deploying the application to Azure App Services. Use the Azure CLI to interact with Azure and deploy the built application. Store credentials securely in Github secrets.