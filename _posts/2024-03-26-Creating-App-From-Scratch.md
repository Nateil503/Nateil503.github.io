## Building an App From Scratch! 

First we created an html file with a simple code.
![3](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7416069c-c393-430a-9210-668f58349d82)

Then we uploaded the code to AWS Amplify, in order to start a Manual Deployment
![2](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/c29d726c-2ace-4629-b538-086f4a3a042e)

![1](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/63b185d0-0c65-4da0-b4fc-8b85c3712ab1)
This is the output of the code before any changes are made. Initial successful deployment.
![4](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/a3273c3d-e30f-4dda-9909-e6b10b516415)

Run Python code using the Python math library. First we create the function using Lambda.
![5](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/70131776-175a-4cfc-8572-22ff52ade717)

Original source code with the Lambda handler highlighted, which is common to all lambda functions. 
![6](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/99a486a0-24a2-4557-b266-7d597a623fbe)

Create a test to determine whether the source code works. After saving and deploying the code, hit the dropdown menu next to test and configure the test event. 
![7](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b9a5ca21-4c8c-4786-96f0-3e44c316f2ea)

Success! The lambda code is working and you will know this due to the "statusCode" being 200 and the "result" being 8.0.
![8](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/599b05dd-2714-453b-9754-3f1897706f5b)

Creating an API and giving it permission to invoke the Lambda Function.
![9](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/38453036-7b43-4537-a022-40bde315b151)

Enable C.O.R.S (Cross Origin Resource Sharing)
![10](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/07336b1c-0a6e-42de-ad92-d2da252b9d8a)

Once the CORS has been activated, we deploy the API. We would need to create a stage/monitor stage actions after validating the resources.
![12](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b568b9db-5742-458c-bb59-e575c8a7608d)
![13](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7c2b85c3-f164-4b88-90d9-08c9cb782b94)

Incorporate a database into the site. Using DynamoDB (noSQL database). Give the lambda function permission to write to the database. 
![14](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/3432e16e-c559-4342-8398-f2f11ce7d611)

We specify permissions using JSON. Input the ARN code copied from the PowerOfMathDatabase (found under additional info)
![15](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/77ee6e0a-746e-48fd-8f62-71f9499b89cf)

Updated source code: in order to use the SDK (Boto.3), insert our math result into our table, and grabbing the current time. 
![16](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7ae4db0f-2f92-4d16-95b9-7bf85dcd2f6f)

The deploy and test is successful, the same as before but when we go to our DynamoDB table, we now have an output. 
![17](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/837be5ee-ce22-4511-9da4-055dc1d0940b)

Update the source Index code; which includes aesthetic changes via the CSS code, the body heading and an input form, and the call API that would hook us up in the API gateway endpoint (using the URL) that would send the information for us to receive the full calculation. Once the file is updated and zipped, we will redeploy it using amplify.

![18](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/a0f59c88-2913-4a87-95f7-de26f0162c33)
![19](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b9d3ef33-115d-4029-9038-8d35515117ce)
![20](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/a7766991-02d9-4af2-9e54-980ce0121533)
The App is complete! Any number being input into fields will produce a calculated output!
![21](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/db76806a-363f-4b9e-8e50-563011ee30b5)


