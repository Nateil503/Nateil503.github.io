**SPORTS DATA IO**

The flow of this project should follow as such: 

![image](https://github.com/user-attachments/assets/3267c1ed-8c96-498a-9ee6-689dd5b44d81)

AWS Lambda function will send a request to the Sports API and return data that will be pushed out to the receiver via SMS or Email. 
The data push will be scheduled through Eventbridge which gives periodic updates and initiates the lambda function to make the request. 
