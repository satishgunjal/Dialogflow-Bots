## UserDetails_CRUD
- This just a demo bot to highlight few important design principles and use cases.
- Bot will provide 4 options to use to Create, Read, Update  and Delete user details
- Based on user choice bot will execute the webhook request to perform the operation
- I am using mongoDB and nodejs
- Route for webhook request is http://localhost:1234/users. For testing you will have to use ngrok for public url access.
  For more details about ngrok ref. https://ngrok.com/download
- Since this demo app I have also created separate route to test each CRUD operation.
  - Create ![Create](/Images/Create.JPG)
  - Read ![Read](/Images/Read.JPG)
  - Update ![Update](/Images/Update.JPG)
  - Delete ![Delete](/Images/Delete.JPG)
  
## Naming conventions. 
- Control the disply order of the intent in Dialogflow
- Please refer **Design/Bot Design Guidelines.md**

## Handling user input and no of tries
- For every user input one default attempt and max two tries are allowed.
- In this Bot I have tried the handle it using custom fallback intent. One can use slot filling feature but it dont have any option to come out of loop if user keep making mistakes.
- This approach increases the number on intents required. For every user input with 3 max tries we will need 3 intent and 3 fallback intents!!
- We can reduce the number of intent required to 2 using webhooks. I will publish that bot soon.

## Using webhook for CRUD operations.
- Webhook is enabled for last intent 'GetmobileNumber'
- Action name is 'UserDetails_CRUD'
- Using VS Code and Nodejs for coding. I will also publish the python webhook code soon.
- EnableWebhookForAgent ![EnableWebhookForAgent](/Images/EnableWebhookForAgent.JPG)
- EnableWebhookForIntent ![EnableWebhookForIntent](/Images/EnableWebhookForIntent.JPG)

## Using MongoDB
- I have mongoDB installed my PC. Or one can use mongoDb Atlas its free as of now.
- Depending on you setup please change the connection string in app.js

## Using ngrok
- To test it we need public url.
- You can host your code on cloud or can use ngrok for testing. I prefer ngrok
