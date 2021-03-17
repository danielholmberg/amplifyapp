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


