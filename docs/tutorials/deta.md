# FastMVC for Deta

FastMVC is a powerful framework for building web applications, and it supports rapid application development for Deta. This tutorial will guide you through the process of creating a new project, running your program locally, and deploying your application to Deta Space. By the end of this tutorial, you will have a working web application hosted on Deta.  

Let's get started!


## Create the Base Project with FastMVC
1. Create a new FastMVC project for Deta: `fastmvc new [PROJECT-NAME] --platform DETA`  
2. Navigate to the project directory: `cd [PROJECT-NAME]`  


## Run your program locally
1. Run the following command to start the local development server: `fastmvc s`. 
2. Navigate to [http://localhost:8000](http://localhost:8000) and check out the project base built already. 
3. End the local server with `ctrl + c`.  


## Push to Deta Space
1. Make sure you have the [Deta Space CLI](https://deta.space/docs/en/basics/cli) installed.  
2. If you are not already logged in through the Space CLI, run: `space login`  
3. Create a new project in Deta Space: `space new`. This will create a 'Spacefile' in your directory.  
4. In the created 'Spacefile', add 'public_routes' like below:  
    ```
    v: 0
    micros:
      - name: project-name
        ...
        public_routes:
          - '*'
    ```  
5. Send your changes to space: `space push`  
6. Navigate to [Deta Space](https://deta.space/) and click on your app


## Setup your DetaBase for this project
1. Navigate to [Deta Space](https://deta.space/) and find your app  
2. Press the '...' button and choose 'Open Project'  
3. Go to the 'Develop' tab. And then the 'Data' tab  
4. Click [Manage Data Keys] and then [Create new data key]  
5. Add the provided key to the '.env' file in your project folder after DETA_PROJECT_KEY=


## Add to the Base Project
1. Back in your local commandline, scaffold a 'post' model with required fields: `fastmvc scaffold post title:str content:wysiwyg draft:bool`  
2. Create an Authentication Framework for Users: `fastmvc auth`  
3. Run your program locally: `fastmvc s`.


## Add a Post
1. Navigate to 'Post'  
2. Create a new post by filling in the required fields.  
3. Submit the post.  
4. Navigate to your project's database in [Deta Space](https://deta.space/) to see your new submission.  


## Update your project in Space
`space push`  


## Setting up a Development Database
You can add the key at the end of this to any project without having to launch your app to Space initially.  
1. Navigate to your Deta Space Canvas  
2. Go to 'Collections'  
3. [+ New Collection]  
4. Name it something like 'development'  
5. Click on 'Collection Settings'  
6. Click on [Create new data key] and save the provided key.  

