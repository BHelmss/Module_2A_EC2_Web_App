# Module 2A EC2 Web App

## Topics Covered in Module 2
- Benefits of EC2
- Instance Types
- EC2 Pricing
- Scaling EC2
- Elastic Load Balancing
- Messaging and Queing
- Additional Compute Services

## Project Description
I decided to do two labs for module 2 since it covered so much material. The first I decided to create a simple web application with html, javascript, and css. It is just an application that asks you to input your saving goal and the timeline you want to save. Then it gives you the required savings each week to reach the goal. After getting the application working how I wanted, I created an EC2 instance, connected to it with SSH, and spun up a http server to be able to host the application from on the remote instance.

## Steps
1. First I created the web application in VSCode with html, css, and javascript. It is simple but sufficient for the purpose of this lab.
   
![image](https://github.com/user-attachments/assets/47756a0f-22f5-4d1f-87b9-1c4c199ac808)

![image](https://github.com/user-attachments/assets/6635ac58-b84d-44f3-8610-4551cdebbbe4)

2. After getting the web app working locally, it is now time to get the instance running on AWS. I named it and chose Ubuntu for the OS since I am already familiar with it.

![image](https://github.com/user-attachments/assets/e585e1c1-00fc-4fda-9171-14cdca6b28a6)

3. Then i selected the instance type as t2.micro this is due to it being free tier elibilbe. But the actual naming convention for instances goes as follows below. the t2.micro is essentially a general purpose instance, second generation, and the smallest size of that generation (micro).
   
![image](https://github.com/user-attachments/assets/33d2e448-66d1-41d3-acbd-1f86630e7eeb)

![image](https://github.com/user-attachments/assets/a3b8b2a6-6679-4208-b06b-9a00d84e99bd)

4. I then created the RSA keypair that I will use to connect to the instance securely after creation. Then i created the security group. This group will have rules allowing ssh only from my ip address and https/http traffic from the whole internet.
   
![image](https://github.com/user-attachments/assets/1ead3a34-f1dd-48eb-937f-602229946d44)

5. The instance can then be launched and connected to. Firstly, i changed the permissions of the .pem(key_file) to 400. I then connected using ssh with the DNS address they give me on the AWS console.
   
![image](https://github.com/user-attachments/assets/f907f180-99db-4d91-8aa6-46ae157e7dbb)

6. Now that I am accessing the root server, I can host my web app from it. I just have to copy the src folder to the server and run a python http server.
   
![image](https://github.com/user-attachments/assets/b70e477c-85de-46d5-9d75-4a442bcd73e0)

![image](https://github.com/user-attachments/assets/90ba7697-706e-4555-b4c0-4b1891bb17bb)


7. Now that the server is running i can go to the url and view it running on port 80 of my EC2 instance.
![image](https://github.com/user-attachments/assets/1ba2b802-127a-4476-ba09-3dd040356cfa)
