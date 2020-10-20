# How to use Azure Cognitive Services Text Analytics

## Overview
This Read Me and its accompanying Jupyter Notebook provides instructions, code, and sample text to walk you through basic machine learning text analysis using Azure Cognitive Services. Specifically, the Jupyter Notebook will show you how to extract key phrases and entities, such as people, locations, and organizations, from a series of lengthy text documents. 

The notebook provides context about the Cognitive Services Python SDK and troubleshooting information so you can take what you've learned and apply it to your own needs! 

* Read Time: 20 min
* Build Time: 20 - 30 min

**Why is this helpful?** 

Doing this kind of text analysis can reduce time and energy required to understand long, open-form text. It can also highlight trends that might otherwise be overlooked. 

**Possible applications**
* Open-form survey responses (what this notebook was originally designed for)
* Customer reviews
* Social media comment analysis 

### Cost Overview
Costs specific to running Cognitive Services Text Analytics are small (<$1), with the bulk of the cost resulting from the use of virtual machines. To reduce cost, do functionality checks and debugging locally. 

When you're done with analysis, stop the Compute engine and delete the resource group.

* **Estimated cost for running this notebook:** <$5

* **Estimated cost for doing your own analysis:** <$10

### What's in the repo:
* text-analytics-notebook.ipynb: A Jupyter notebook that contains explanatory text and code blocks that will walk you through setting up and using Azure Cognitive Services
* TextFiles folder: Sample text files for you to run
* Images: Screenshots and other supporting images for the Jupyter notebook.


## Setting up Azure Cognitive Services
If you're new to Cognitive Services, here's what you'll need to do to get set up.
You will need a Microsoft Azure subscription. you do not already have one, set up a Microsoft Azure subscription. You can sign up for a free trial at: https://azure.microsoft.com/free 

### Step 1: Set up Azure Machine Learning

2. If you already have an Azure Machine Learning workspace, navigate to Azure Machine Learning studio and sign in. Otherwise, follow these steps to create a new workspace:
    1. Sign into the Azure portal using the Microsoft account associated with your Azure subscription.
    2. Select **＋Create a resource**, search for **Machine Learning**, and create a new Machine Learning resource with the following settings:
        * **Workspace Name**: enter a unique name that gives some info on what you're using the service for
        * **Subscription**: choose your Azure subscription
        * **Resource group**: create a new resource group with a unique name
        * **Location**: choose any available location
    3. It takes a few minutes for the workspace resource to be created. When it's done, click tne new **"Go to resource"** button and click **"Launch Now"** to open the Azure Machine Learning ("ML") studio (or go to: https://ml.azure.com). 

    4. In ML Studio, click the ☰ icon at the top left to view menu options. You can use these pages to manage the resources in your workspace. 
    
        We'll be using two of these pages for this project: 
        * **Notebooks**, which is where we'll load and run our Jupyter notebook, and 
        * **Computer**, which is where we'll set up the machine learning compute engine.

[TO DO: INSERT SCREENSHOT]

## Step 2: Create an Azure Machine Learning compute instance

To run the Jupyter notebook, you will need a compute instance in your Azure Machine Learning workspace. If you already have one, start it; otherwise, follow these instructions to create one:

1. In Azure Machine Learning studio, go to the Compute menu option (under Manage near the bottom).
2. On the Compute Instances tab, click "Create" to create a new compute instance. Input the following settings:
    * **Compute name:** enter a unique name
    * **Virtual Machine type:** CPU
    * **Virtual Machine size:** Standard_DS11_v2
3. It takes a few minutes for the compute instance to start. While we wait, let's go to the next step!

## Step 3: Set up an Azure Cognitive Services resource
If you don't already have one, use the following steps to create a Cognitive Services resource in your Azure subscription:

1. In another browser tab, open the Azure portal at: https://portal.azure.com
2. Click the **＋Create a resource button**, search for Cognitive Services, and create a Cognitive Services resource with the following settings:
    * Name: Enter a unique name.
    * Subscription: Your Azure subscription.
    * Location: Any available location.
    * Pricing tier: S0
    * Resource group: Create a resource group with a unique name.

3. Deployment will take a few minutes, but that's okay! We won't need it just yet. Onward to the next step!

## Step 4: Download and import this notebook into Azure Machine Learning Studio.
You can either download or clone this GitHub repo to your computer and upload into the Machine Learning ("ML") Studio, or follow the steps to clone directly into ML Studio:

1. In ML Studio, navigate to the Notebooks page (under Author). 

2. Under My files, use the 🗋 button to create a new file with the following settings:
    * **File location:** Users/your user name
    * **File name:** Get-Files
    * **File type:** Notebook
    * **Overwrite if already exists:** Selected

3. When the notebook has been created, check that the compute instance you created is selected in the **Compute** box, and that its status is **Running**. Then, in the blank cell at the top of the notebook, paste the following code:

    ```!git clone https://github.com/jenfoxbot/text-analytics-walkthrough.git```

4. Click the ▷ button next to the cell to run the code in the cell. This will clone the repository files from GitHub.

5. When the code has finished running, use the ↻ button under My files to refresh the folder view. Verify that a folder named **text-analytics-walkthrough** has been created. This folder contains the Juypyter notebook and other files you'll need in this walkthrough.

6. Close the Get-Files.ipynb notebook tab (click the "X" at the top of the notebook view).

## Step 5: Open the text-analytics-walkthrough notebook and run through the code!
You're nearly ready to tackle text analytics! 

1. Open the *text-analytics-notebook.ipynb* notebook in the **text-analytics-walkthrough** folder. 
    If you're using the notebook editor in Azure Machine Learning studio, use the ≪ button to collapse the file explorer pane and give you more room to focus on the notebook tab.
2. Read through the notebook and run the code cells as you go.

## Aside: Tracking expenses and setting a budget

1.  Go to your Azure Portal home page
2. Selecting the **Resources Group** for this service.
3. In the new window, select the **"Cost analysis"** section (under "Cost management" on the left-hand side). 
There you can see a cost breakdown of each service as well as forecasted costs.
4. You can also set a budget by clicking on the "Budget" drop-down and selecting "Create a new budget". 
    *Note that this will send you an e-mail alert when you are close to your budget limit, it will not stop services.*

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
