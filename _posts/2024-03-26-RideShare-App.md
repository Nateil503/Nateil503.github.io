## RideShare for Unicorns!

**Here we will create a rideshare app for Unicorns.**

Starting by creating an account on ArcGis. This will allow for location tracking which is necessary for the app. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/dd28709d-4a60-4024-bbf4-e293e5360f42)


Create the repository through CodeCommit.

![1 2](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/c98f5468-d578-4505-8a25-744ab1a0dabb)

After creating the repository, we want to grant permission for the users. We would attach policies directly so that the user would be able to use codecommit. 

![2](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/647b7b19-30d5-4037-bb9b-c2b8fca5439b)
![3](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/02fe19ec-e1c2-46f6-965e-9685cc1cab03)

Next, we want to generate Git credentials for the user. 
![4](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/5b881453-7db9-4ca7-b661-5fdadb38fda8)

Then we want to open up CloudShell within the repository and input the cloned url and provide the username from the git repository. 
![5](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/fceb807b-96ab-449f-aecf-828bba4cdacf)
![6](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/9f3afb50-7c22-4fcb-a987-9ef8707deb4c)

Depositing code/information from an S3 bucket. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/83084ca5-32ca-416d-9664-3f3f4cbde597)
We have to include the information from the repository into the code, they will then ask us for information.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/2af7a7a3-a7bd-44ab-ae6d-0ec31fa883cb)

I ran into some trouble due to the source of the S3 bucket being in a different region, however I switched the origin of the url to the repository url and then executed the git push. After it successfully generated the username and password request, I entered the same credentials as before and was able to validate the objects. 


![8](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/f4db4860-5f99-46de-a217-aa613192b947)

**Create a new repository** 

![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7d1ee3ee-d18e-4564-b0b0-dcdc0f9cef74)
Create a new service role then save and deplpoy. Make sure Allow box is checked.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/479ae02c-2c11-4018-b8b8-52d65ea44d29)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b870e02f-0acc-44a6-84cb-07953b84290a)

After the success message. We will check to see if the link is valid. Voila!
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/1ceb6b28-b4a9-43bc-bafd-ac6a329a145d)

Now to update the code just to see if we are having continuous deployment on the site. We will update this text from "how does this work?" to "how does this thing work?"

![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/60240beb-3a51-49da-a3e4-4e5a92e83a6d)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7d0992d2-be22-4360-98eb-b6b5d24b41a4)
We will then commit changes. (Input author name and email for trailing purposes) Provision -> Build -> Deploy will occur again. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/ed3e556c-ebc6-4974-9459-c34c697a290b)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/c9c654b5-eee7-49b0-b794-8b09ba6b63ef)

**Allowing user interaction**
We are going to use Cognito to allow users to sign up for the services. You do this by creating a user pool and choosing the sign-in options. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/6c66f638-c810-4e1a-a5b3-05ff8bc86610)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/d8f37c4d-9ac9-4c15-940a-8f776c87c1ef)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/48f55636-f14f-4c5d-8bb5-84b2bac05e7b)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/560f35b3-7bcb-4627-8b71-c4295cba8e6d)
You will be able to customize every attribute to go along with the user interface and their options on signing up. Also cannot be changed after user pool has been created.

An email for verification can be automated in order to send emails to the user. You can customize this address. Send email with cognito will be better for a temporary start.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/d419a2ae-4bc8-4fbc-bbba-53a4c2dd575c)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/aae81297-5810-4f3c-815b-9370e0611018)

You will need to retain the credentials for the User Pool by copying the ID, then copying the client ID at the bottom of the page.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/4ca05b08-d472-4c64-b505-be0711d1657a)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/ae14fdb6-7a60-471e-8f98-561e96611e27)

Return to the Repository and enter the JavaScript folder, then open the configuration code. You will then input the User Pool & Client IDs. Make sure the region is updated as well.

![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/147a5489-f4bb-4370-a4e4-35092689aa58)

**Let's Sign Up!**
Once the the updates have deployed we will refresh the site and attempt to sign up. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/d7cbc20f-3098-4727-9f42-a6a752cb5ec4)
It will then generate an email to send a verification code, which you will then input into the required fields. 

![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b5428b8c-6afd-4556-8776-5ecd61f1fd3f)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b2bf19bf-75e8-45e9-8acc-19cff1cd95d7)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/91b0e711-b3bb-4bfd-998c-d2ce8f36e8c3)

Amazing right?!

The authentication token will then be provided on the page where the map is supposed to be.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/ed922236-8305-440e-92cf-7b3ee4417f71)
We will then create a table using DynamoDB
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/0adb523e-0202-469e-8fe4-a83bd84adbd1)

Once the table is created we will grab the ARN from the General Information section right under 'additional info'
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/0f40ff53-6809-4cda-89b2-7b914f500d5a)

**Lambda Integration**

Create a role for lambda permissions 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/e847092e-511f-40c0-a8c3-71fb33ef7322)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/e68eaf8b-914a-41c8-835e-5bd9a2386f56)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/cf6f58e8-cbb0-48f2-a491-387dbed1f9d7)

Now we need to add permissions. Which is to write to a DynamoDB table. We would select the role and then create an inline policy. Best practice is to only give the required permission for the task at hand, to avoid unnecessary interference. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/046351bd-7239-4dfd-b8b1-bd235d5f3c28)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/2c9aec63-db13-483e-ac41-afc86e9823d3)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/1adf9a4b-8cb8-4682-ae1a-8fc2d1748ab1)

Now we will create the lambda function itself. Don't let the runtime default to the updated node. We specifically need Node.16. Change the execution role to an existing role which would be the lambda function we just created.

![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/f3db8116-1e0f-4b29-8716-22e455b6dce4)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/0a3937c4-19cd-467a-807c-affa0a4e74d0)

Once we've created the function we can now edit the code. AWS provided a sample code for the rideshare, to which you can edit certain elements. I've decided to change the names up a bit. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/9d79c5e8-8c76-4c3c-ac09-9b040754ef9d)
**Deploy the code any time changes are made!**

Create a test event so that you can see if the code works.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/ebd67dd4-c1b0-4b5f-819c-2ad4cf4d3714)
Success! The 201 and the unicorn credentials are an indicator that the code test was successful. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/d1ee2cb6-da46-4052-ba04-c02f8627dba6)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/dd1aea50-e514-4905-b968-996c2f7589e5)

**Create an API**

We would need to create an API to ensure the flow of information is seamless and that we face no technical difficulties. When choosing an endpoint; edge-optimized is better for cross-internet actions.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/1f0abc3b-8a92-4c92-947c-0f25b17b1754)

We would create an authorizer to authenticate calls next, which is basically the way of connecting the API Gateway's JWTs or JSON webtokens that are returned by Cognito. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/468a9e25-edb2-4d2d-a8dd-526e5b937b85)

Now the authorizer token that we copied earlier comes into play now. Input it then hit 'test authorizer' if the result is a code of 200, it was a success.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/2e1d29d0-cf52-419d-b90e-482a64318151)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/90991233-fd3c-4acb-94cd-9b649f0b2aca)

Next we need to create a resource so that we can connect to the Lambda function. The URL used to invoke the API Gateway call is different from the URL used for the site (Amplify), which is why it's necessary to check the CORS box. (Cross-Domain)


![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/10e31bdf-6e41-4c5d-ad60-b7e0560dafcf)

We then create the method so that the Lambda function is integrated. Make sure to toggle the proxy integration. After creating the method, edit the method and in the drop down Authorization menu... select the user pool authorizer.
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/6db462e7-6dd6-4188-9c6d-b98456c6c6cf)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7ea50c52-5b5f-4a87-b0d8-e097576341a2)

Deploy the API. Then grab the invoke URL. Input the URL into the config code from before. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/c118520a-825c-4391-a15d-44540d6384fa)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/7eb5f489-9c98-460c-9776-832eda080d0a)

Voila! Here's the map. Click any location and a unicorn should be on the way!
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/48d93441-8e43-446a-9724-390dbd6a3c30)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/eaa30474-c044-400d-8779-844c5407f500)

The DynamoDB should be updated with the items returned, with the credentials of the ride requestor. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/58394abb-37b3-41cf-b7f1-323b241ac44b)



