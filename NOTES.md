# Notes

## [Module 1: Deploy and Host a React App](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/module-one/?e=gs2020&p=build-a-react-app-intro)

In this module you will create a React application and deploy it to the cloud using AWS Amplify’s web hosting service.

  1. Create a React application
  2. Initialize a GitHub repository
  3. Deploy your app with AWS Amplify
  4. Implement code changes and redeploy your app

### 1. Create a React application
```npx create-react-app amplifyapp```
```cd amplifyapp```
```npm start```

### 2. Initialize a GitHub repository
```git init```
If you have previously configured multiple git hosts, be sure to use the correct one. In my situation the correct Host with an SSH already added to the GitHub profile is:
  Host danielholmberg.dev
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa_danielholmberg_dev
```git remote add origin git@danielholmberg.dev:username/reponame.git```
```git add .```
```git commit -m “initial commit”```
```git push origin master```

## [Module 2: Initialize a Local Amplify App](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/module-two/)

In this module you will install and configure the Amplify CLI.

  1. Install and configure the Amplify CLI
  2. Initialize the Amplify app

**Amplify CLI** – The Amplify CLI allows you to create, manage, and remove AWS services directly from your terminal.

### 1. Install and configure the Amplify CLI
```npm install -g @aws-amplify/cli```
```amplify configure```

### 2. Initialize the Amplify app
```amplify pull --appId d3bpie8sqvao6l --envName staging```

? Choose your default editor: *Visual Studio Code*
? Choose the type of app that you're building *javascript*
? What javascript framework are you using *react*
? Source Directory Path:  *src*
? Distribution Directory Path: *build*
? Build Command:  *npm run-script build*
? Start Command: *npm run-script start*
? Do you plan on modifying this backend? *Y*

## [Module 3: Add Authentication](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/module-three/)

In this module you will use the Amplify CLI and libraries to configure and add authentication to your app.

  1. Install Amplify libraries
  2. Create and deploy an authentication service
  3. Configure your React app to include authentication

**Amplify libraries** – The Amplify libraries allow you to interact with AWS services from a web or mobile application.

**Authentication** – In software, authentication is the process of verifying and managing the identity of a user using an authentication service or API.

### 1. Install Amplify libraries
```npm install aws-amplify @aws-amplify/ui-react```

### 2. Create and deploy an authentication service
```amplify add auth```

? Do you want to use the default authentication and security configuration? *Default configuration*
Warning: you will not be able to edit these selections.
? How do you want users to be able to sign in? *Username*
? Do you want to configure advanced settings? *No, I am done.*

```amplify push --y```

### 3. Configure your React app to include authentication

