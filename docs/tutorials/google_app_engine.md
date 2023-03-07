# FastMVC for Google App Engine

FastMVC is a powerful framework for building web applications, and it supports rapid application development for Google App Engine. This tutorial will guide you through the process of creating a new project, setting up Firestore, configuring a service account, running your program locally, and deploying your application to the cloud. By the end of this tutorial, you will have a working web application hosted on Google App Engine.

If you're new to Google App Engine, we recommend walking through the [Google App Engine Tutorial](https://cloud.google.com/appengine/docs/flexible/python/create-app) first to get familiar with the workflow expected for launching an app in Google App Engine.

Let's get started!


## Create the Base Project with FastMVC
1. Create a new FastMVC project for Google App Engine: `fastmvc new [PROJECT-NAME] --platform GOOGLE_APP_ENGINE`  
2. Navigate to the project directory: `cd [PROJECT-NAME]`  
3. Scaffold a 'post' model with required fields: `fastmvc scaffold post title:str content:wysiwyg draft:bool`  
4. Create an Authentication Framework for Users: `fastmvc auth`  


## Google App Engine Console
1. Go to [Google Cloud Console](https://console.cloud.google.com/projectselector2/home/dashboard) and create a new project. 
Note: If you have not already enabled Billing for your Google Cloud account, you will have to do so  
2. In the left menu, scroll down until you find [Firestore](https://console.cloud.google.com/firestore/data/panel). Click into the 'Data' subdirectory and then select 'Native Mode' and your region.  


## Service Account
1. Navigate to 'IAM & Admin' > '[Service Accounts](https://console.cloud.google.com/iam-admin/serviceaccounts)'  
2. Click on [+ Create Service Account](https://console.cloud.google.com/iam-admin/serviceaccounts/create), provide a name and optionally a description. Click [Create and Continue].  
3. In section 2 'Grant this service account access to a project', choose Role => 'Owner'. Click [Continue] and then [Done].  
4. Click on the newly created Service Account and go to 'Keys' tab.  
5. Click [Add Key] -> [Create New Key] -> select JSON -> [Create].  
6. Place the downloaded JSON into the 'ignore' folder in your project. 
7. Delete the 'service-account-file.json' and change the json file name in the .env file to the name of the downloaded JSON.


## Run your program locally
1. Run the following command to start the local development server: `fastmvc s`. 
2. Navigate to [http://localhost:8000](http://localhost:8000) and check out the project base built already. 


## Add a Post
1. Navigate to 'Post'  
2. Create a new post by filling in the required fields.  
3. Submit the post.  
4. Navigate to [Firestore Data](https://console.cloud.google.com/firestore/data/panel) to see your new submission.  


## Push to the (g)cloud!
1. Run `gcloud init` and select you account and your project name.
2. Run `gcloud app create` and choose your region when prompted.
3. Deploy your app: `gcloud app deploy`  
4. Browse your deployed app: `gcloud app browse`