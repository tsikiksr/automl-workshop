# automl-workshop
Repository with instructions, notebooks and data files for automated ML worshop.

## Pre-requisites
+ Azure subscription. Preferably use your existing organization/personal subscription. If needed, you can get a free trial subscription with some credit [here](https://azure.microsoft.com/en-us/free/)

## Overview
In this workshop, you will go over the following steps:
1. Set up Azure Notebooks project to do the workshop
1. Configure your Azure Machine Learning service workspace so it is ready for automated ML training
1. Run the Energy demand forecasting notebook, including:
   + Read the data and prepare it for training (split to train/validation/test)
   + Configure and run automated ML training job to get the best model
   + Analyze and test the results
   + Deploy the model to Azure Container Instance (ACI)
   
## Scenario
This scenario focuses on energy demand forecasting where the goal is to predict the future load on an energy grid. It is a critical business operation for companies in the energy sector as operators need to maintain the fine balance between the energy consumed on a grid and the energy supplied to it.

## Configure Azure Notebooks

#### Log in

1. Go to https://notebooks.azure.com/
1. Click "Sign in" on the top right corner
1. Use your Azure subscription credentials to log in

#### Clone workshop repo

1. From Azure Notebooks home page, click "My projects"
1. Select "Upload GitHub repo"
1. In the "Upload GitHub Repository" window, enter the the following GitHub repository: https://github.com/tsikiksr/automl-workshop
1. The rest of the fields will be automatically populated, leave them be
1. Make sure "Public" is checked
1. Click "Import" and wait for the clone process to complete (can take a few minutes)
1. Click "Run on Free Compute" to start the Jupyter server

## Run automated ML notebooks

### Configuration
The configuration notebook will create and prepare an Azure Machine Learning service workspace. You only need to run it once to create the workspace, which can then be used for multiple experiments, model training, and deployments. 

1. From the Jupyter file list, select the "configuration.ipynb" notebook to open it
1. If prompted for kernel, select "Python 3.6" and click "Set Kernel"
1. Proceed to the first code cell and hit "Run", you should see that the SDK version is at least the version that is expected
1. Proceed to the next code cell, to enter your subscription id in the appropriate palce (<my-subscription-id>)
    + To retrieve your subscription id, go to https://portal.azure.com/ and search for "subscriptions", then select "subscriptions" from the results (the one with the key icon)
    + Locate your subscription and copy the "subscription id" text (it is a 32 character text in the format of XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX)
    + Go back to the notebook and replace the <my-subscription-id> (including the brackets) with the actual subscription id
    + Keep the rest of the parameters as is
    + Run the cell
1.  Go to the next cell and run it, you should be prompted to open a login window, then do the following:
    + Copy the 9 character code in the output
    + click the link to open the login window (https://microsoft.com/devicelogin)
    + In the login window, paste the 9 character code and hit "Accept" when prompted to.
    + Go back to the notebook and wait for the authentication to finish.
    + You should get the message: "Workspace not accessible. Change your parameters or create a new workspace below". That is ok, it means that the workspace was not found, so you can process to the next code cell.
1. Run the cell to create the new workspace (might take a few minutes to complete)
    + Once completed successfully, verify that the workspace was actually created by going to https://portal.azure.com/ and search for "my-automl-workshop-ws" in the search box. selecting the workspace will open it, and you'll be able to view the workspace. This is your Azure Machine Leanring service workspace, which include all of the resources you'll need for training and deploying ML models.
    + this cell will also persist the worksapce details into a config file, so it is easily retrieved for future use.
1. Run the next cell to verify the configuration and the config file and wait for the output. verify the configuration.
1. Run the next cells **one by one (wait for each one to complete)** to install the additional dependencies
  
Well done! You have completed the configuration notebook, and you are now ready to move on to the energy demand forecasting notebook.


### Energy demand forecasting notebook

1. Go over the "auto-ml-forecasting-energy-demand-end2end.ipynb" notebook (until "Deploy" section), cell by cell. Each cell has the details of its content, wait for each one to complete before starting the next cell.

### Deployment
1. go over the "Deploy" section of the notebook. wait for each step to complete, image creation and service deployment takes several minutes to complete.

Congrats! You have completed the workshop successfully!

# References
+ https://aka.ms/automatedmldocs
+ http://aka.ms/automatedmlsamples
+ http://aka.ms/automatedml

Ask questions, send feedback: AskAutomatedML@microsoft.com


