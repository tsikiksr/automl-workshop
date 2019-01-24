# Instructor notes for automated ML workshop

Recipe for creating and conducting automated ML workshop using Azure Notebooks backed by DSVM compute (for running the notebook and the compute)

## Preparations

### Prepare DSVM

1. Go to Azure portal and create a Data Science Virtual Machine (with enough cores to serve the audience). Use username and password for admin access and write them down. recommended to use the following: user: automl , pass: AutoML123!@#
1. Make sure port 8000 is open for all incoming traffic (Networking tab)
1. Once the DSVM is running, log on to the console and update the Azure SDK to the latest version using the following commands:  
sudo -i /anaconda/envs/py36/bin/pip install --upgrade azureml-sdk
sudo -i /anaconda/envs/py36/bin/pip install --upgrade azureml-sdk[automl,notebooks,explain]

## Workshop walkthrough

### Subscribe to Azure

Get a Free trial from here https://azure.microsoft.com/en-us/free/ 

### Configure Azure Notebooks

#### Log in

1. Go to https://notebooks.azure.com/
1. Click "Sign in" on the top right corner
1. Use your Azure subscription credentials

#### Clone workshop repo

1. From Azure Notebooks home page, click "My projects"
1. Select "Upload GitHub repo"
1. In the "Upload GitHub Repository" window, enter the the following GitHub repository: https://github.com/tsikiksr/automl-workshop
1. The rest of the fields will be automatically populated, leave them be
1. Make sure "Public" is checked
1. Click "Import" and wait for the clone process to complete (can take a few minutes)

#### Attach to DSVM

(**Instructor only**: go to the DSVM and write down the IP address. you have to do this right before the workshop starts because the IP is dynamic and can change over time)

1. When the cloning process will end, you should land inside the "automl-workshop" project. If this is not the case, click to enter the project
1. The project will probably be in a running state. If you can't select a compute from the dropdown (above the file list on the left), click the "shutdown" checkbox (or press the "h" key on the keyboard) to shu down the server
1. Click on the compute dropdown and select "Direct compute", then in the "Run on new direct compute target" window that opened, fillin the following:  
    Name: automl-workshop  
    Enter an IP: <the IP of the DSVM>  
    Username & Password: <as defined in the DSVM>
1. Click "Validate" and wait for the green "Your DSVM configuration has been validated..." message. If you get an error message, try validate again, sometimes the error is intermittent. Once succeeded, click "Run" to open the the Jupyter notebook home page. You should be able to see the notebook list. If not, there is a problem with running the server on the DSVM, see the troubleshooting section.

### Run automated ML notebooks

#### Configuration

1. Go over the "configuration.ipynb" notebook

#### Energy demand forecasting notebook

1. Go over the "auto-ml-forecasting-energy-demand-end2end.ipynb" notebook (until "Deploy" section)

#### Deployment
1. go over the "Deploy" section of the notebook

### Consumption
TBD

#### Consume from Power BI
TBD

## Troubleshooting
TBD
