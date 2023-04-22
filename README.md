# telegram_memobot
telegram bot to store memo items into googlesheet and allows user to maintain the memos


# Requirements
- Google Sheet with a table of 2 columns , sheet name as "memo"
- Telegram chatbot token, see https://t.me/BotFather

# Getting Started - Google App Script Project
[1] Goto https://script.google.com/home 

Click "New Project" 

![image](https://user-images.githubusercontent.com/32192638/229261975-fa19519d-0a10-4e20-9642-065f30de4679.png)


[2] Rename the project

Click on the "Untitled project" to rename the project as something else. Example, "memobot".

![image](https://user-images.githubusercontent.com/32192638/229262072-5c90f86e-3459-42f5-b283-120079de578a.png)


[3] Write the scripts, copy paste from below template url :

https://github.com/WingsMaker/telegram_memobot/blob/main/telegram_memo_bot.txt


[4] Update the values of ownerid in the script using your own telegram chat_id.

var ownerid = "....";

[5] Update the values of token in the script using the bot token.

Find your Telegram chatbot token by logging into the BotFather in Telegram, selecting your bot, 
and clicking the "API Token" button.
( see https://www.youtube.com/watch?v=aNmRNjME6mE )

Change the value of statement, paste the bot token into here.

var token = "....";

[6] Add the codelib library using the script ID given.

To make the code shorter, use the "codelib" library. 

Use this google app script editor page, find the "Libraries +" option on the left

![image](https://user-images.githubusercontent.com/32192638/233791136-b16c60af-624f-4180-b3c4-c3742b39c357.png)

Click on the +  and find the text box prompt for "Script ID *"

![image](https://user-images.githubusercontent.com/32192638/233791197-98492977-bfe9-4e6e-bd86-2ab6014c056f.png)

Enter this value "1XH9ezlLoC939C4Xgkl-1sBSh8JXDlSYwiDMBeutpTk9GXBqI3K9dBBxK"

![image](https://user-images.githubusercontent.com/32192638/233791243-5ec1a99f-774b-4594-9ab9-b78e4d26ec85.png)

Click "Look up" and then click the blue button "Add" 


[7] Update the values of sheetid in the script using google sheet url.

![image](https://user-images.githubusercontent.com/32192638/233791641-d1d3339e-ec0a-479b-afbc-48b8db21d31e.png)

Where to get the sheetid ?
- Create a googlesheet and get the hyperlink/URL from the browser
- Remove the prefix "https://docs.google.com/spreadsheets/d/" and the suffix "/edit...",  the reminding string is the sheetid.


What to do with this sheet ?

- Rename the worksheet (tab) name as "memo"
- Format the sheet as a 2 columns table, no need title row
- Add first row with A1 = "#webhook" and B1 = webhook_id ( see [9] for webhook_id )
that's it about the sheetid
( no need to rename the googlesheet filename, its optional )

var sheetid = ".....";


[8] Deploy as google web app

In the Google App Script project, go to "Publish" in the top navigation bar. 

Under "Deploy as web app", select "Deploy". This will open a pop-up window. 

Your web app URL will be listed in the "Current web app URL" field.

Click on the "Deploy - New Deployment"

![image](https://user-images.githubusercontent.com/32192638/209758084-a48fdfd0-4eb8-45be-af04-1642c3c05ed8.png)

Click "Select type - Web App"

![image](https://user-images.githubusercontent.com/32192638/209758240-b3d00b5c-09de-4355-be1d-b6193269409f.png)

Fill in the form and click "Deploy".
( for more see https://www.youtube.com/watch?v=-AlstV1PAaA )

![image](https://user-images.githubusercontent.com/32192638/209758768-29dda612-80c7-425e-8a39-e3e80d2fe5bc.png)

Copy the web app url to the clipboard for later use.

[9] Where to get the webhook_id ?

When you google app script compiled as web app, it has a hyperlink URL.

Use this google app script editor page, find the blue [Deploy] button

Use the path to find the url :  "deploy -> manage deployments > web app URL"

The URL in the format https://script.google.com/macros/s/...../exec

By removing "https://script.google.com/macros/s/" and "/exec" , the long string is the webhook_id.

What's next:

Enter this value into the cell B1 next to cell A1 having "#webhook"



[10] Run the "setWebhook" function for only once to make sure actual telegram bot 
able to callback this google web app.

![image](https://user-images.githubusercontent.com/32192638/229262318-1d1e0980-745b-4362-8363-200e6848be5e.png)

Your telegram memobot is ready !
