**SPORTS DATA IO**

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
![image](https://github.com/user-attachments/assets/c6cc2326-5052-489f-940c-f18027c72fb0)

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

