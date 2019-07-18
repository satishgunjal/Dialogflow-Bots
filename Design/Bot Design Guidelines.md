## Mind Map Design
1. Use shapes/nodes as per the legends. Ref. file  **Bot Mind Map Legends.jpg**
2. Split the flow in small tasks and call it states. Give number to each state. make sure to have one state per page. 
3. Spliting the flow in multiple states will make it readable and easy to mantain.
4. Keep only one state per page
5. State numbering example. 
    - For medium Bot flow 50 states should be enough. For 50 states we can start numbering from 000,020,030... and end with 980.
    - Each state will have maximum 19 intents. (If required you can keep it more than 19 but its better to have less intents per state)
    - So state 000 will have intents from 000 to 019. e.g. 000.Default Welcome Intent, 001.Default Fallback Intent,002.UserWantsToSelectDetails, 003.UserWantsToSelectDetails_Try1.......016.UserProvidesChoice_Try2_Fallback
    - Number at the start of each intent will make sure that all the intents are arranged in required sequence as per our design.
    - Also it will make each intent name unique. e.g. We may want to use 'UserWantsToAddDetails' intent name in multiple states for diiferent context. Unique state numbering will make intent name unique and easy to understand
6. Intent naming format. e.g. xxx.UserProvidesFirstName, xxx.UserProvidesFirstName_Try1, xxx.UserProvidesFirstName_Try2 
7. Fallback Intent naming format. e.g. xxx.UserProvidesFirstName_Fallback, xxx.UserProvidesFirstName_Try1_Fallback, 
    xxx.UserProvidesFirstName_Try2_Fallback
8. Context naming format. e.g. awaiting_first_name, awaiting_first_name_1, awaiting_first_name_2
9. Context lifespan should always be 1

