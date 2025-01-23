**SPORTS DATA IO**

The flow of this project should follow as such: 

![image](https://github.com/user-attachments/assets/3267c1ed-8c96-498a-9ee6-689dd5b44d81)

AWS Lambda function will send a request to the Sports API and return data that will be pushed out to the receiver via SMS or Email. 
The data push will be scheduled through Eventbridge which gives periodic updates and initiates the lambda function to make the request. 

**PROCESS** 
Log into the console and go to the 'SNS' page. Create a topic. This one will be 'gd-topic' for Game Day Topic. 
![image](https://github.com/user-attachments/assets/ae1f77f1-3efe-4976-9ed5-71a1e9ad5f2c)
Make sure to choose standard for the topic type. 

Next we will create a subscription for the updates to be sent through. 
![image](https://github.com/user-attachments/assets/ac778cd3-55b1-498f-8d36-b0aafec4e357)
![image](https://github.com/user-attachments/assets/1625be27-68c5-4361-a92b-8f1b75d40eda)
