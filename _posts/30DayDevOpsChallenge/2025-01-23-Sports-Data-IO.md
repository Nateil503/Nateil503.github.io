# SPORTS DATA IO

The flow of this project should follow as such: 

![image](https://github.com/user-attachments/assets/3267c1ed-8c96-498a-9ee6-689dd5b44d81)

AWS Lambda function will send a request to the Sports API and return data that will be pushed out to the receiver via SMS or Email. 
The data push will be scheduled through Eventbridge which gives periodic updates and initiates the lambda function to make the request. 

**PROCESS** 

**Create the Topic**
Log into the console and go to the 'SNS' page. Create a topic. This one will be 'gd-topic' for Game Day Topic. Make sure to choose standard for the topic type.
![image](https://github.com/user-attachments/assets/ae1f77f1-3efe-4976-9ed5-71a1e9ad5f2c)
 
Next we will create a subscription for the updates to be sent through. 
![image](https://github.com/user-attachments/assets/ac778cd3-55b1-498f-8d36-b0aafec4e357)
![image](https://github.com/user-attachments/assets/1625be27-68c5-4361-a92b-8f1b75d40eda)
![image](https://github.com/user-attachments/assets/156c3a80-7a93-4808-af66-0bef42a87f6d)

After subscribing, you should receive an email asking for confirmation of the subscription. As well as a status message from the dashboard claiming confirmation. 
![image](https://github.com/user-attachments/assets/fb7dd480-6d3c-4f18-8fcd-9678620707e6)
![image](https://github.com/user-attachments/assets/e7649218-2a10-4316-8186-a9efa3963cc5)
![image](https://github.com/user-attachments/assets/1e045556-e0d3-4a6e-930b-f705b8f9efc4)


**Create The Lambda Policy**
Go to the IAM section, probably best to open it up in a different tab. Go into policies and create one. When selecting a service, choose SNS. It will then ask you what to input, where we will switch over to the JSON tab. 
![image](https://github.com/user-attachments/assets/88dd1c36-f722-4aab-9b5d-47c7a624a2c2)

When we get over to the JSON tab it will give us the ability to code exactly what we want. Copy your created code/cloned repository and paste here. You will need to gather credentials for the highlighted portion. You can find these credentials in the topic tab. Make sure when pasting that it is within the quotation marks. 
![image](https://github.com/user-attachments/assets/9c39aa3b-37e1-459f-ab3e-bf4a560ce472)
![image](https://github.com/user-attachments/assets/a577e7d4-d354-40c6-b416-5e9130f377f7)

**Create The Lambda Role** 
Next we will create a role to assign the policy to. You will also find this in the IAM section. Choose AWS Service for the type and Lambda for the use case. 
![image](https://github.com/user-attachments/assets/338b85f7-1a4f-4538-b7c1-9c7fc5d28daa)
![image](https://github.com/user-attachments/assets/c65ba210-6daf-489d-b64a-1fbf69f2d214)

Once the role has been created we're going to assign the policies to the role. Search up the name of the policy you created a couple steps back, then add an additional role called the Basic Execution Role. 
![image](https://github.com/user-attachments/assets/3982ff5a-7f58-43b9-810e-ec8f44e79c97)
![image](https://github.com/user-attachments/assets/0ce14e7f-26f9-4ef1-a200-37f62629a372)

**Create The Lambda Function**
Create the Lambda Function and make sure it says 'Author from Scratch'. Choose your desired programming language. Then click the dropdown of the default execution role and choose 'use an existing role'. Here you will select the role created earlier. 
![image](https://github.com/user-attachments/assets/811411cf-d302-47c1-8025-0a16acf16f2d)

After fully creating the role, they will give you a visual section for the code. This is where you will paste the Notification code. After pasting, click the deploy option on the left. 
![image](https://github.com/user-attachments/assets/62601eaf-b0af-4d15-8240-c7d51fd37a5f)

Here you will grab the API from your SportsDataIO account. Go into account and it will take you to the area with your subscription. I have more interest in football than basketball so I opted for the NFL subscription. 
![image](https://github.com/user-attachments/assets/577acd6f-aea8-488a-8c47-58a9e7749cb9)

Go into the environment variables and edit them. This would be found under 'configuration' + 'environment variables'. Select Add Environment Variable. There you will provide the API key as well as the SNS topic key. 
![image](https://github.com/user-attachments/assets/3ae384a7-8cd3-47df-b688-8e932481f877)

**TEST**

Once you have your environment variables set up, you will go in and make any corrections in the code to make the information more accurate. This could be the time-zone as well as what sport. You will then test the code to see if it works, you'll do so by going into the 'test' tab and creating a new test. 
![image](https://github.com/user-attachments/assets/c68c73c8-2edf-42ad-8db6-966452fd5968)

I ran into an issue here, so it is imperative to make sure the required information matches up accurately. I kept getting error messages because there was a discrepancy within the url. After fixing that, and choosing an earlier game date... I was able to pull this information. 
![image](https://github.com/user-attachments/assets/0b72a47a-1dd7-4f6e-b816-b87034d7e355)


After confirming the endpoint works, continue on to testing. When testing, you should receive a confirmation message. 
![image](https://github.com/user-attachments/assets/3a42e04d-8c69-46bc-a2fc-8699dff1219c)

You should also receive a push notification in your email. 
![image](https://github.com/user-attachments/assets/c1a65357-f51c-47ce-9130-c8453797c8c4)

**SCHEDULING**

Go to 'Eventbridge' within the applications. You will need to create a rule. 

![image](https://github.com/user-attachments/assets/a83aaa2b-9473-45a5-a14a-7ae32a32d3a3)

The next step is to determine its frequency. We're gonna go with a recurring schedule. The option of Cron-based scheduling allows for a specific time to update, rather than a set frequency of updates (eg. every 10 mins). You can get more specific through the Cron expression. 
![image](https://github.com/user-attachments/assets/c16a2557-a51a-453b-a1ee-a2a7581a5436)


The value boxes coordinate with the specific time frames as well as the frequency. In the screenshot, the 9-23 represents the hours that it will be running (Military time), and the '/2' represents the frequency. So this reads that from 9am-11pm you will get updates every 2 hours. 

Next, select your target. Since we are coding with a Lambda function, we would need to choose Invoke. The screen will auto-scroll down to the JSON script, and from the drop down menu you choose the function you want to invoke. It will be the 'gd_notifications' that we created before. 
![image](https://github.com/user-attachments/assets/241a5154-5544-4c1a-b59d-e67d4c579788)

![image](https://github.com/user-attachments/assets/5cce86f3-f54f-4ddc-8442-ac287f87075d)

Continue to click next until the rule has been fully created. The dashboard should look like this after. 
![image](https://github.com/user-attachments/assets/392bec3d-fd44-4adf-86e2-959c9c209425)

Depending on your frequency, and when you made the rule, the push notification will vary. I finished the project really close to one of the update times and here we are receiving an update.
![image](https://github.com/user-attachments/assets/2dbca1f7-ac00-4109-8200-501062bdcdef)
