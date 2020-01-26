# openapi-tf-example

# Get started

## The essentials

- Download Terraform v0.12.x [here](https://www.terraform.io/downloads.html)
- You will need Node v12.x from [here](https://nodejs.org/en/download/)
- Git, to clone this Repo, from [here](https://git-scm.com/downloads)
- Create a free AWS account (requires credit card) [here](https://aws.amazon.com/)
- Finally, download the [AWS CLI tool](https://aws.amazon.com/cli/) 
- Setup your AWS local profile, see [this](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html) guide how it's done.

## To get the API running
If you meet all the pre-requisites, do the following

- In your AWS development account create the S3 bucket for your Terraform state files.
  - Optionally, encrypt the S3 bucket and enable versioning such that you can do a rollback.
- ```git clone``` this repo.
- Change your AWS credentials profile name in these files: 
  - ```./env/dev/remote-backend.tf```
  - ```./env/dev/dev.tfvars```
- Run ``` npm install ``` and then execute ``` npm run dev-init ```, this will:
  - Initialize the Terraform project for the 'dev' environment, and synchronize the state with the cloud stored .tfstate file.
  - If you run it a second time, it will fail on the workspace creation, this is not an issue (the workspace already exists)
- Run ```npm run dev-full``` to package the source code (locally in ```./env/dev/dist```) and to prepare the deployment to your AWS account.
  - Confirm with ```yes``` to deploy, anything else will cancel the deployment

See my full guide on dev.to for more information about this project

## VS Code plugins used

- [StandardJS](https://marketplace.visualstudio.com/items?itemName=chenxsan.vscode-standardjs)
- [Terraform](https://marketplace.visualstudio.com/items?itemName=mauve.terraform)
- [OpenAPI Editor](https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi)
- [OpenAPI Designer](https://marketplace.visualstudio.com/items?itemName=philosowaffle.openapi-designer)

ps. I'm aware the gulp file doesn't exit nicely, i'm not an expert. Any pull requests or issue reports with pointers is definitely appreciated.