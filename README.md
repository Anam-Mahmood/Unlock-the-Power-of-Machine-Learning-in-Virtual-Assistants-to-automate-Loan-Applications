# CP4D Banking Demo

## Step 1. Create Watson Studio service 

video 1

1.	Login to your IBM Cloud account: 
 
2.	Within your IBM Cloud account, click on the top search bar to search for cloud services and offerings. Type in “Watson Studio” and then click on Watson Studio under “Catalog Results”.

3.	This takes you to the Watson Studio service page. Select a region, “Lite” plan (Free) and give your service a unique name. Click on “Create” and this creates a Watson Studio instance for you.

4.	Once the service instance is ready, you will be redirected to the Watson Studio page. Click on the “Get Started” button to launch Watson Studio in a new tab. This might take few minutes to set up the service.

5.	Under the heading “work with data” you will find a link that says, “Create a project”. Click on “Create a project”. Next, click on “Create an empty project”.

6.	On the new project page, give your project a name. You will also need to associate an IBM Cloud Object Storage instance to store the data set.

7.	Under “Select Storage Service”, click on the “Add” button. This takes you to the IBM Cloud Object Store service page. Leave the service on the “Lite” tier and then click the “Create” button at the bottom of the page. You are prompted to name the service and choose the resource group. Once you give a name, click “Create”.

8.	Once the instance is created, you’re taken back to the project page. Click on “refresh” and you should see your newly created Cloud Object Storage instance under Storage.

9.	Click the “Create” button at the bottom right of the page to create your project.

10.	Click on the “Add to project” button on the top right corner. From the pop-up window select “Data”.

11.	In the column, on the right, click on “browse”. Navigate to the folder where you downloaded the data set to and select “insurance.csv”

12.	Watson Studio takes a couple of seconds to load the data, and then you should see the import has completed. To make sure it has worked properly, you can click on “Assets” on the top of the page, and you should see your insurance file under “Data Assets”.

## Step 1.1: Create and Run AutoAI experiment

video 2.1

1.	Once you have added the data set, click on the “Add to project” button on the top right corner. This time select “AutoAI experiment”.

2.	On the New AutoAI Experiment page, give a name to your project.

3.	Next, you need to add a Watson Machine Learning instance. On the right side of the screen, click on “Associate a Machine Learning service instance”.

4.	On the Associate service page, click on the “New Service” button on the right side of the screen. From the pop-up screen, select “Machine Learning”.

5.	Select the appropriate region. It is recommended to build your machine learning service instance in the same region that you created your Watson Studio service. Select the “Lite” (free) plan. Give your instance a unique name. Click on “Create”.

6.	Once you create your machine learning service, on the next page, check the box with your machine learning service instance. Next, click on “associate service” on the right corner.

7.	Once the service is successfully associated, you will be redirected to new AutoAI experiment page. Click on “Reload” on the right side of the screen. You should see your newly created machine learning instance. Click on “Create” on the bottom right part of your screen to create your first AutoAI experiment!

8.	After you create your experiment, you are taken to a page to add a data source to your project. Click on “Select from project” and then add the insurance.csv file. Click on Select asset to confirm your data source.

9.	Next, you see that AutoAI processes your data, and you see a What do you want to predict section. Select the expenses as the Prediction column.

10.	Next, let's explore the AutoAI settings to see what you can customize when running your experiment. Click on Experiment settings.First, you see the data source tab, which lets you omit certain columns from your experiment. You choose to leave all columns. You can also select the training data split. It defaults to 85% training data. The data source tab also shows which metric you optimize for. For the Binary Classification, and for other types of experiments, such as regression, it is RMSE (Root Mean Squared Error), AutoAI defaults to Accuracy. Either way, you can change the metric from this tab depending on your use case.

11.	Click on the Prediction tab from within the Experiment settings. There you can select from Binary Classification, Regression, and Multiclass Classification.

12.	Lastly, you can see the Runtime tab from the Experiment settings this shows you other experiment details you may want to change depending on your use case.

13.	Once you are happy with your settings, ensure you are predicting for the expense’s column, and click on the run Run Experiment button on the bottom-right corner of the screen.

video 2.2

14.	Next, your AutoAI experiment runs on its own. You see a progress map on the right side of the screen which shows which stage of the experiment is running. This may be Hyper Parameter Optimization, feature engineering, or some other stage.

15.	You have different pipelines that are created, and you see the rankings of each model. Each model is ranked based on the metric that you selected. In the specific case that is the accuracy. Given that you want that number to be as high as possible, you can see that in the experiment, the model with the highest accuracy is at the top of the leaderboard.

16.	Once the experiment is done, you see Experiment completed under the Progress map on the right-hand side of the screen.

17.	Now the AutoAI has successfully generated eight different models.

18.	In our case, you see the accuracy value is 0.775, from Pipeline 3. Click on “Pipeline 3”.

19.	On the left-hand side, you can see different “Model Evaluation Measures”. For this particular model, you can view the ROC curve.

20.	On the left-hand side, you can also see “Feature Transformations”, and “Feature Importance”.

21.	On the left-hand side, click on “Feature Importance”. You can see here that the most important predictor of the loan eligibilty is the duration of your current residency. This is by far the most important feature, followed by others in loan and if you own a property.

## Step 1.2. Create a deployment and test your model

video 3

1.	Once you are ready to deploy one of the models, click on “Save As” at the top-right corner of the model you want to deploy. Save it as a “Model” and name your model as you want. Click on “Create”.

2.	Once the model is successfully saved, click on the “View in project” in the green notification on the right side of the screen. Alternatively, you can also find your model saved in the “Assets” tab under “Models”.

3.	Next, you are taken to a screen that has the overview of the model you just saved. Click on “Promote to deployment space” on the top right corner of your screen. Alternatively, if you’re doing it from the Assets tab, then under the “Models” section, click on the 3 dots on the right side of your screen and click “promote”.

4.	On the Promote to space page, you need a target space to promote your model. Click on “New space +” on the right side of your screen.

5.	Next, on the Create a deployment space screen, give your space a name, make sure the right cloud object storage is selected, and select your machine learning service instance. For this experiment, selecting the machine learning service is mandatory as we need to build a prediction model. Then click on “Create”.

6.	Once the space is ready, click on “Close” in the pop-up and you will be redirected to the promote to space page. You see your newly created space under the “Target space”. Once you’re happy with your selections, click on “Promote”.

7.	Once the model is successfully promoted, you will see a green notification box, click on “deployment space” in the notification. Alternatively, you can also find your deployment spaces when you click on the hamburger sign on the top left most side on your screen.

8.	You will be redirected to the deployments page, where you will find your promoted model. Hover over the row, to see a rocket shaped icon, click on the icon to deploy you model.

9.	In the dialog box, select “Online” as your deployment type, give your deployment a name and click “Create”.

10.	Click on the “Deployments” tab to see the status of your deployment.

11.	Once the deployment is completed, click on the name your deployment.

12.	On this page you find the API references, endpoint and code snippets to help you integrate your model with your applications. Copy the endpoint of your model and save it as we will need it later.

13.	To test your model, click on the “Test” tab. You can select a row from the data set and enter the data in the fields. Enter the values from the dataset, and then click on the “ Add to Predict” button at the bottom and then on "Predict".

---

## Step 2. Create API KEY

1. Click on manage next to your account name and in the drop down list choose “Access (Iam)”.
2.	Click on API keys on the right side.
3.	Click on "Create" and give a name to the Api Key. Copy and save the API Key as you will not be able to see it again. You can also download the API KEY.


## Step 3. IBM cloud functions

1.	Within your IBM Cloud account, click on the top search bar to search for cloud services and offerings. Type in “Functions” and then click on Functions under “Catalog Results”.
2.	Click on get started.
3.	Click on Current namespace and create a namespace.
image namespace

4.	Under "Action" tab click on "Create" and then "Action"
5.	Give the action a name, choose the “Default package, and a runtime of your choice, in our case we are using "Python 3.7".
image actions

6.	Once the action is created you will need to add an API KEY under the "Parameters" tab that we created in Step 2.
7.	Under the "Code" tab, paste the below code.

` # main() will be run when you invoke this action
# @param Cloud Functions actions accept a single parameter, which must be a JSON object.
# @return The output of this action, which must be a JSON object.

import sys
import json
import requests

def main(dic):
    # NOTE: you must manually set API_KEY below using information retrieved from your IBM Cloud account.
    API_KEY = dic["api_key"]
    token_response = requests.post('https://iam.cloud.ibm.com/identity/token', data={"apikey": API_KEY, "grant_type": 'urn:ibm:params:oauth:grant-type:apikey'})
    mltoken = token_response.json()["access_token"]
    
    header = {'Content-Type': 'application/json', 'Authorization': 'Bearer ' + mltoken}
    
    # NOTE: manually define and pass the array(s) of values to be scored in the next line
    payload_scoring = {
	"input_data": [
		{
			"fields": [
				"CheckingStatus",
				"LoanDuration",
				"CreditHistory",
				"LoanPurpose",
				"LoanAmount",
				"ExistingSavings",
				"EmploymentDuration",
				"InstallmentPercent",
				"Sex",
				"OthersOnLoan",
				"CurrentResidenceDuration",
				"OwnsProperty",
				"Age",
				"InstallmentPlans",
				"Housing",
				"ExistingCreditsCount",
				"Job",
				"Dependents",
				"Telephone",
				"ForeignWorker"
			],
			"values": [
				[
					dic["CheckingStatus"],
					dic["LoanDuration"],
					dic["CreditHistory"],
					dic["LoanPurpose"],
					dic["LoanAmount"],
					dic["ExistingSavings"],
					dic["EmploymentDuration"],
					dic["InstallmentPercent"],
					dic["Sex"],
					dic["OthersOnLoan"],
					dic["CurrentResidenceDuration"],
					dic["OwnsProperty"],
					dic["Age"],
					dic["InstallmentPlans"],
					dic["Housing"],
					dic["ExistingCreditsCount"],
					dic["Job"],
					dic["Dependents"],
					dic["Telephone"],
					dic["ForeignWorker"]

				]
			]
		}
	]
}
    response_scoring = requests.post('https://us-south.ml.cloud.ibm.com/ml/v4/deployments/e7a8d7c5-5f14-49ab-b236-bd3326dcbabb/predictions?version=2021-08-05', json=payload_scoring, headers={'Authorization': 'Bearer ' + mltoken})
    print("Scoring response")
    print(response_scoring.json())
    result = response_scoring.text
    result_json = json.loads(result)

    result_keys = result_json['predictions'][0]['fields']
    result_vals = result_json['predictions'][0]['values']
   
    result_dict = dict(zip(result_keys, result_vals[0]))
  
    no_percent = result_dict["probability"][0] * 100
    print("no_percent: ", no_percent)
    yes_percent = result_dict["probability"][1] * 100
    print("yes_percent: ", yes_percent)
    
    predict = result_dict["prediction"]
    
  
    
    final = ('Your application is presenting a ' + predict + ' application with a risk probability of: %.0f%%'% yes_percent)
    print("final: ", final)
    return { 'message': final }
    `
8. In the below line, replace the link with your machine learning deployment link that you copied from Step 1.2.12:
 `response_scoring = requests.post('https://us-south.ml.cloud.ibm.com/ml/v4/deployments/e7a8d7c5-5f14-49ab-b236-bd3326dcbabb/predictions?version=2021-08-05', json=payload_scoring, headers={'Authorization': 'Bearer ' + mltoken})`

8.	Lastly under the "Endpoints" tab, check the "Enable as web action" and copy the public URL.
9.	In the code above, for testing you can replace the values in json section with any value from the dataset and invoke the function to get an output.

image invoke functions

---

## Step 4. Watson Assistant

1. Within your IBM Cloud account, click on the top search bar to search for cloud services and offerings. Type in “Watson Assistant” and then click on Watson Assistant under “Catalog Results”.
2. This takes you to the Watson Studio service page. Select a region (make sure all your services are in the same region), “Lite” plan (Free) and give your service a unique name. Click on “Create” and this creates a Watson Assistant instance for you.
3. Once the service instance is ready, you will be redirected to the Watson Assistant page. Click on the “Launch Assistant” button to launch Watson Assistant in a new tab. This might take few minutes to set up the service.
4. Click on "Assistants" and then "Create" assistant.
6.	Give your assistant a name and click "Create" assistant.
7.	Once your Assistant is created, click on "add an action or dialog skill" and then click on "Upload Skill".

Your machine learning model is now connected to your Watson Assistant. You can click on "preview" and test it out!






