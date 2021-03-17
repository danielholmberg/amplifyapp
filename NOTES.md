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

```amplify console```

## [Module 4: Add a GraphQL API and Database](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/module-four/)

In this module you will use the Amplify CLI and libraries to configure and add a GraphQL API to your app.

  1. Create and deploy a GraphQL API
  2. Write front-end code to interact with the API

**API** – Provides a programming interface that allows communication and interactions between multiple software intermediaries.

**GraphQL** – A query language and server-side API implementation based on a typed representation of your application. This API representation is declared using a schema based on the GraphQL type system. (To learn more about GraphQL, visit [this page](https://graphql.org/learn/).)

### 1. Create and deploy a GraphQL API

```amplify add api```

? Please select from one of the below mentioned services: *GraphQL*
? Provide API name: *amplifyapp*
? Choose the default authorization type for the API: *API Key*
? Enter a description for the API key: *DEMO*
? After how many days from now the API key should expire: *7*
? Do you want to configure advanced settings for the GraphQL API: *No, I am done.*
? Do you have an annotated GraphQL schema?  *No*
? Do you want a guided schema creation?  *Yes*
? What best describes your project: *Single object with fields*
? Do you want to edit the schema now? *y*

```amplify push --y```

 This will do 3 things:
  1. Create the AppSync API
  2. Create a DynamoDB table
  3. Create the local GraphQL operations in a folder located at src/graphql that you can use to query the API

There are 3 main functions in our app:
  1. **fetchNotes** - This function uses the API class to send a query to the GraphQL API and retrieve a list of notes.
  2. **createNote** - This function also uses the API class to send a mutation to the GraphQL API, the main difference is that in this function we are passing in the variables needed for a GraphQL mutation so that we can create a new note with the form data.
  3. **deleteNote** - Like createNote, this function is sending a GraphQL mutation along with some variables, but instead of creating a note we are deleting a note.

## [Module 5: Add Storage](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/module-five/)

In this module you will add storage and the ability to associate an image with the notes in your app.

  1. Create a storage service
  2. Update a GraphQL schema
  3. Update your React app

**Storage service** - Storing and querying for files like images and videos is a common requirement for most applications. One option to do this is to Base64 encode the file and send as a string to save in the database. This comes with disadvantages like the encoded file being larger than the original binary, the operation being computationally expensive, and the added complexity around encoding and decoding properly. Another option is to have a storage service specifically built and optimized for file storage. Storage services like Amazon S3 exist to make this as easy, performant, and inexpensive as possible.

### 1. Create a storage service

```amplify add storage```

? Please select from one of the below mentioned services: *Content*
? Please provide a friendly name for your resource that will be used to label this category in the project: *imagestorage*
? Please provide bucket name: *<your-unique-bucket-name>*
? Who should have access: *Auth users only*
? What kind of access do you want for Authenticated users? *create, read, update, delete*
? Do you want to add a Lambda Trigger for your S3 Bucket? *N*

## Conclusion

You have deployed a web application using AWS Amplify! You have added authentication to your app allowing users to sign up, sign in, and manage their account. The app also has a scalable GraphQL API configured with an Amazon DynamoDB database allowing users to create and delete notes. You have also added file storage using Amazon S3 allowing users to upload images and view them in their app.