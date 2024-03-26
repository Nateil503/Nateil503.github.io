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

Incorporate a database into the site.
