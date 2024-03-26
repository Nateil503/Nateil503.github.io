## RideShare for Unicorns!

**Here we will create a rideshare app for Unicorns.**

Starting by creating the repository.

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

