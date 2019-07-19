## UserDetails_CRUD
- This just a demo bot to highlight few important design principles and use cases.
- Bot will provide 4 options to use to Create, Read, Update  and Delete user details
- Based on user choice bot will execute the webhook request to perform the operation
- I am using mongoDB and nodejs
- Route for webhook request is http://localhost:1234/users. For testing you will have to use ngrok for public url access.
  For more details about ngrok ref. https://ngrok.com/download
- Since this demo app I have also created separate route to test each CRUD operation.
  - Create> http://localhost:1234/users/create
  
- The state machine design approach. Spliting the flow in multiple sates.
  - Naming conventions. Control the disply order of the intent in Dialogflow
  - Handling user input and no of tries
  - Using webhook for CRUD operations.
  - Using MongoDB
  - Using ngrok
