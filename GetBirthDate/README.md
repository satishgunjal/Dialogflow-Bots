## Important Points
1. Updating the context from webhook
2. Updating the parameters from webhook
3. Verify birth year value using regex
4. Max 3 attempt includes successfull intent hit but invalid input, fallback intent hit and no input.
5. I am handling 3 tries for collecting the birth date using intent and falback intent.
6. Not handling tries for 'GetFirstName'. Bot 'UserDetails_CRUD' covers how to collect first name and handle tries.
7. I am handling 3 tries for collecting the birth year using webhook.
8. Using webhook simplifies the design. We will need only 1 intent and 1 fallback intent to collect input. For comparison ref 'GetBirthDate' page where we have to use 3 intent and 3 fallback intent to handle 3 tries.
9. Intent webhook will verify the input value where fallback intent webhook will increase the 'noOfTries' counter.
10. Only create the parameters which are used to extract the values from training phrases. If parameter like 'noOfTries' is not used to extract any value then dont create it in Dialogflow. Dialoglfow will initialise the values of all the parameter whenever that particular intent is hit. Since 'noOfTries' parameter value is not comming from training phrases, Dialogflow will always initialise it with 'null'. So every time we read the value of 'noOfTries' from 'session_vars' it will be 'null'
11. To handle this create the parameter like 'noOfTries' inside webhook under context 'session_vars'. It will be avilable throughout the duration of chat and Dialogflow wont reset it after intent hits.

## Important Points About Webhook Code
1. I amusing API V2 only. Please refer Dialogflow documentation for V2 API format.
2. Read and write values only from 'session_vars' context. Its lifespan ia 100 and it will hold all the values for entire duration of chat. 
3. I have created function 'GetParameterValueFromSessionVars(parameterName, outputContexts)' which will read values only from session variable.
4. Since 'session_vars' will contain the values of all the paramteres, only update the required parameters in 'session_vars'. Rest all parameters will be retained by Dialogflow.
5. Similarly only update the required context and rest all content will be retained by Dialogflow
6. To delete the content simple set the lofespan to '0' and DIalogflow will delete it
7. 

## Reference
1. DialogFlow tutorial: Setting context from your inline webhook using contextOut
   https://miningbusinessdata.com/dialogflow-tutorial-setting-context-from-your-inline-webhook-using-contextout/
   Note: NodeJs code is above tutorial uses API V1 sysntx.
2. Youtube- Dialogflow webhook 101- https://www.youtube.com/playlist?list=PLJKszJbOREcVPJxJEfpj3CTqDEm1BQHuP
3. For V2 webhook response fromat ref. https://dialogflow.com/docs/reference/v1-v2-migration-guide-fulfillment#webhook_responses
