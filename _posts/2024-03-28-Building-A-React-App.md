## Building a React App!

**Here we are going to build a react app with the components of Amplify, Cognito, and the use of GitHub hosting.**

First we will create a checklist to keep ourselves in order. A great tool for this would be eraser.io where we'd be able to create a diagram as code. Pretty cool. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/af5df273-466b-4924-923a-5a6d9e33b5f1)

We would need to then, install the amplify cli in order to have better access to the AWS accounts. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/ab782eb7-44cf-4bcc-b94c-28cd4fd18c49)

Create a new user and attach policies directly. This specific policy
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/bce06285-53f3-40c1-9acb-5a3a063b6c50)
Create an access key and input it into the CLI
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/dc6db5d4-cde7-4d54-ab06-fb75d7b02558)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/081b92a6-254f-47c2-9ccd-99b299e781d0)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/4a8f0b03-4553-405f-b51e-10a8037261b7)

After successfully installing the CLI across AWS, we then change directories to go deeper into the files of the app. We will be logging into the user that we've previously created and save a deployment state. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/9959d49e-d48a-4b88-8b26-1ff5aae0ccbf)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/01274059-a1f3-4b91-93f7-97e39183f485)

Keeping up with the checklist:
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/992f305a-75ff-4b3c-8b9b-bb8f7da77af2)

Once we return to amplify, we notice that the app we created in the CLI is present within the amplify console. Our next step is to add authentication with cognito. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/c92470c6-fe1e-4e64-87a7-4675eabb6c57)

We'll make our changes depending on what you want present in the app 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/13d02c56-6c4e-4d8d-8e92-81ae5a76eac3)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/3a249136-e86d-4782-a819-684659d8a52d)

We'd run npm start, which will take us to a local hosting address where we'd be able to sign up and log in. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/0d57daed-7540-4fd4-8760-5147f7075b2f)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/b7b90d4f-8b43-43dd-b1e5-5278e43a22f3)

After we've successfully created an account and received the confirmation code. We can check Cognito and refresh to see the user pool updates. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/41b08536-0785-4755-a9eb-63df343a46dd)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/8eb85b51-79b1-4817-9fba-d894488ecfe6)

The explanations for each functionality within the code. The Authenticator line is key*
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/e3baf804-25cd-4e10-89b6-ccf1a4050535)

Grabbing source code from the repository to create new quiz files which would provide data for the quiz site to work. Make sure the names match the repository code or else the input will not work. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/3e10b41c-80de-462d-b4ae-85417920776e)

Once all code is inputted we can refresh the localhost tab and you will see the data has been updated. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/526958ca-4298-4301-b594-b5e2de540ec1)

**PUSH CODE FOR GITHUB**
Now that we've got a running source code and app, it's time to push it to the front end so that the public can interact with it. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/887d752c-a505-4be6-859a-b4c73cb81556)

Create a new repository
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/82d5266e-cde5-4980-ad4c-ce49a4eeb109)

I ran into a bit of an issue due to not having the git software downloaded on the console I'm using. Once I downloaded git, the interface of the code changed a bit and now certain pathways are open. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/1ee66bf0-5e2c-4f66-9eb1-e6233ced8c81)

The gitpush commands were not working since I did not have a master branch available, so I ended up linking the git software I just downloaded, to my github account to be able to do so. Now because there was no master branch, the main couldn't be created. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/205caa79-6885-430b-97b4-f9a172e471a9)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/0c6d9f29-6b2c-49f1-91d9-c33d3627b6bb)

The repository is up and running 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/679d2ca4-574d-4607-8355-0b81b4caaa81)

Now go back to Amplify to add a repository branch for the source code to be hosted on Github. Once we have chosen the backend source and are getting through the building of the app, make sure the CI/CD continuous deployment is checked so any updates will be automatically integrated into the app. You will need to create a new role for the Amplify backend in order to have that seamless connection. 
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/17ace537-5d99-4433-8c36-29b8196e5993)
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/15e8ad8a-f440-44cd-ae57-8df3dfd2f53d)


Now that we've added roles and updated the backend, we can now deploy the amplify app which will give us an actual URL instead of the local host
![image](https://github.com/Nateil503/Nateil503.github.io/assets/114696114/d674a995-35d5-4745-98f5-ec0200030416)






