# Labwiev and PLC Communication

**Introduction to the Project:**

In my project, I provided PLC Communication over Labwiev and controlled it over Labwiev. The main reason why I chose this project was the importance given to Labwiev in line with my internship in the defense industry this year. Labwiev is used frequently, especially by Roketsan.

Before starting the project, I made the application via Labwiev with Siemens' series S71200 PLC. The reason I chose the S71200 was that I had used this PLC series before. I will get help from the Tia Portal programming interface for the working principle of this. The Tia Portal interface I use also belongs to the V15 version.

![image](https://user-images.githubusercontent.com/73780930/215638916-ae91da48-1233-4e81-bbc4-19d6d388a5da.png)

I wanted to explain the project with step-by-step process steps in order to be understandable and to explain the situations I applied in these steps.

# 1. Stage

I make my programs to be used ready, I open Tia Portal V15 series and Labwiev interface. Here, I am using Labwiev's 2022 model for 40 days free of charge.

![image](https://user-images.githubusercontent.com/73780930/215639044-17b508e2-e41f-406e-8295-e2f7ee21afc9.png)

In this project, we will need additional modules of Labwiev, namely libraries. Here I will provide the download via Labwiev Package Manager.

![image](https://user-images.githubusercontent.com/73780930/215639137-43cce94b-9f86-4b86-96db-6100040c6093.png)


Here, we will need Labwiev Datalogging and Supervisory Control Runtime and Labwiev Datalogging and Supervisory Control Module to use the OPC Servers Configuration, which is the critical part, and also the active state of Labwiev's interface with PLC. This part will be as seen in the additional picture and we will provide the download process.


![image](https://user-images.githubusercontent.com/73780930/215639261-d32f6848-5c2f-4809-92f1-4dc8f6eaadc6.png)


# 2. Stage

Let's go back to the PLC side after making adjustments on Labwiev. Here, let's open Siemens' Tia Portal screen and select our PLC model.


![image](https://user-images.githubusercontent.com/73780930/215639319-a15fca56-a3ac-4180-8ae9-2f2ea6fad82d.png)

![image](https://user-images.githubusercontent.com/73780930/215639340-7919a951-7a0e-4c7e-a9b2-2de94c116ab3.png)


Finally, this figure appears on our screen. From here, let's introduce our inputs and outputs in the left main menu. I can promote it through show all tags.

![image](https://user-images.githubusercontent.com/73780930/215639389-5bf3b6bf-8db8-450b-9c3b-a496441027da.png)


Thus, I assigned my input and output addresses as it will appear on the table. I will provide this simultaneous implementation on Labwiev and I will provide this process by assigning the same classes.


![image](https://user-images.githubusercontent.com/73780930/215639423-d247f3e9-81ef-4edf-a2e6-e5b3d4448341.png)



By switching from Main to Ladder diagram, I set up a basic circuit layout here.
After this basic circuit layout, I will learn the IP address of the PLC, which we call Network IP, which will play an important role in transitioning to Labwiev.


# 3. Stage

One of the key parts of our project is the OPC server control part. For NI supported Labwiev, our OPC server must also be installed via the site address.


![image](https://user-images.githubusercontent.com/73780930/215639537-3def8fc6-45ed-4e7d-a988-69944de1cf8a.png)


As seen in the picture, we will start our communication part by assigning work on the upper left side. Below are my latest works.


**Part 1 - Default Input Settings**

![image](https://user-images.githubusercontent.com/73780930/215639699-e5448574-8a0a-4a87-bee7-7ac281b66af8.png)

By assigning our input settings in the OPC Server section, the names of our input and output addresses that we assigned in the PLC simulation will play an important role in entering here.


![image](https://user-images.githubusercontent.com/73780930/215639774-1961c58d-205b-426a-8850-6657824bf222.png)


I set the input of our Siemens S71200 model, which we should have used here. Thus, I have taken the basic step of providing communication.


![image](https://user-images.githubusercontent.com/73780930/215639803-9c1abd27-da47-4633-be06-8af6c362b249.png)


In the window that opens, I make the choice because we will communicate over the TCP protocol. Then we need to get the IP of the Wi-Fi network connected to our computer. In this, we can see all of them if an ethernet or wireless network-based connection is provided to the computer. I prefer to use it over ethernet. Here we can see the connection of my wireless network in the attached picture.


![image](https://user-images.githubusercontent.com/73780930/215639836-7399df5f-6346-404f-9aef-f99801113617.png)

As seen in the picture, we can see our Wi-Fi network.

![image](https://user-images.githubusercontent.com/73780930/215639884-bb661be2-ca05-4dae-9cbe-fe4bd777fb79.png)

![image](https://user-images.githubusercontent.com/73780930/215639896-0b819fe0-0f28-4ba0-86c0-68c6d91a21c2.png)

![image](https://user-images.githubusercontent.com/73780930/215639906-436558bc-ab72-4801-9625-e4b70308862e.png)


In the last 3 pictures, there are default settings. These are available for the change of settings in communication. I have completed here with the next option without making any changes.


**Part 2 - Adding Resources**

![image](https://user-images.githubusercontent.com/73780930/215639973-6534b79f-53aa-4786-8b96-fb64ed3aedc9.png)

![image](https://user-images.githubusercontent.com/73780930/215639987-47c61c2d-35ed-448f-95f6-e6f98897b934.png)


In this section, we will add our source file. We will associate it with PLC Tia Portal and I will switch to the I/O Server part.


![image](https://user-images.githubusercontent.com/73780930/215640022-2fbd548a-3e09-44d7-a7de-b8d3150dfff7.png)


I also choose our Siemens S71200 model and move on to the next stage.


![image](https://user-images.githubusercontent.com/73780930/215640073-35743902-3aea-43f0-bf10-e726cfe10a45.png)


The connection options were set in Tia Portal and the IP of the PLC side was learned in the previous step and added as Device ID on Labwiev.


![image](https://user-images.githubusercontent.com/73780930/215640134-498147f9-dc99-40bd-95ad-a457e0aa87e3.png)


The purpose of putting this picture is that we can learn the IP of the PLC model we choose through Profinet. It is also seen in the Subnet Mask.


![image](https://user-images.githubusercontent.com/73780930/215640198-fb2db1c7-246c-44ed-857a-d2b3dd43c39e.png)


![image](https://user-images.githubusercontent.com/73780930/215640222-3adc06be-0b12-451c-a6f7-b30f628a783f.png)


![image](https://user-images.githubusercontent.com/73780930/215640236-bae963bd-b128-4076-a216-6a5c566c18be.png)


![image](https://user-images.githubusercontent.com/73780930/215640288-7d79289f-1de4-4966-bc9e-b0c779a0269a.png)


![image](https://user-images.githubusercontent.com/73780930/215640318-685df0be-06bc-4b33-b4f0-1dbf329d1780.png)


![image](https://user-images.githubusercontent.com/73780930/215640345-a5da56e7-fd7d-42f8-863e-3642e42d3dd6.png)


![image](https://user-images.githubusercontent.com/73780930/215640356-c32d4f9b-6573-4e22-b474-84c1ba00b0f8.png)



In the last 7 images, the default settings of the source files can be changed. I didn't need any changes in my project here.


![image](https://user-images.githubusercontent.com/73780930/215640403-fed59a1d-0d55-4760-a541-b9e28590a29c.png)



After this part is over, we can see on the screen that it is assigned to our source in this way in the upper left part. Now we can assign the addresses and names of the inputs and outputs with the add option.

**3. Part-Input Output Address Assignments (via Labwiev)-Making with the Help of OPC Sever**


![image](https://user-images.githubusercontent.com/73780930/215640470-6eefe328-e75e-4ab7-90d4-f22005de5bbf.png)


![image](https://user-images.githubusercontent.com/73780930/215640487-9be59af6-fe2d-476b-907e-ea6d27b3c81a.png)


In these 2 images, the M0.0 address named “input” written on the PLC, which is our input, and the “exit” address for the output, Q0.0 address, have been added to the OPC server iel Labwiev.


![image](https://user-images.githubusercontent.com/73780930/215640515-22631298-12d0-447b-864d-891cd1ccd23e.png)


![image](https://user-images.githubusercontent.com/73780930/215640520-068b9648-f7e6-46ca-86d0-346de20b720c.png)


As a result of these stages, the situations that appear on both Tia Portal and OPC Server are as follows.
However, our outputs are not active. As a result, we need to activate them.


# 4. Stage

![image](https://user-images.githubusercontent.com/73780930/215640588-a2cdab3d-a1d4-4361-81d0-d97b6c5c866f.png)


We open the file we added as device with the QC option. Likewise, we connect with the Siemens Tia Portal Go Online option and become active in our 2 applications.

![image](https://user-images.githubusercontent.com/73780930/215640627-ea5e20e3-2445-44f8-9536-93505c184ec6.png)

When Tia Portal is activated, it can output in this way, but we also need to design the control interface over Labwiev.

![image](https://user-images.githubusercontent.com/73780930/215640660-261ad435-f0d5-4751-88e4-23262ca1462d.png)

![image](https://user-images.githubusercontent.com/73780930/215640676-e0c4a1f4-a35b-437a-8655-7e7412d6b4e6.png)

Thus, our OPC Server QC outputs are assigned as BOOLEAN and we start to output value values. In Labwiev, we will set the interface and provide control.

# 5. Stage

![image](https://user-images.githubusercontent.com/73780930/215641604-c1ac594d-7363-4c9a-9cdd-21fed3033352.png)

Let's open the file with Blank Project.

![image](https://user-images.githubusercontent.com/73780930/215641678-95249e3d-b221-46b9-b4e5-d51aad00c46c.png)

![image](https://user-images.githubusercontent.com/73780930/215641702-f98707da-e3f2-447a-9032-6f469ec26f5b.png)


We provide I/O Server plugin and I associate our interface with Tia Porta.


![image](https://user-images.githubusercontent.com/73780930/215641721-f41fea36-0371-49d3-8a12-2e73a711ef13.png)

![image](https://user-images.githubusercontent.com/73780930/215641668-faf7eb91-e95f-4c91-8094-96064f5faca4.png)

![image](https://user-images.githubusercontent.com/73780930/215641736-7fbcc24b-261e-44ae-bc66-994d9b9f9989.png)


![image](https://user-images.githubusercontent.com/73780930/215641758-7afa2159-73a2-4e18-a7c4-ceae3f1f1d9b.png)


As a result, it can appear as active in our inputs and outputs.


![image](https://user-images.githubusercontent.com/73780930/215641800-808b2665-2e51-4218-99c3-ff4d68545c70.png)


When I check again in the control interface, I see that there is no problem. Then I enter the Labwiev interface.


![image](https://user-images.githubusercontent.com/73780930/215641850-9a67c54c-fbd5-4ac2-be90-58a8df4964b1.png)


This is the part of the interface that I associate the interface with in Labwiev. In the lower part, I can see that the button is not pressed and the communication part is provided as soon as it is pressed.


![image](https://user-images.githubusercontent.com/73780930/215641902-149a8c06-1a05-4ff7-bb23-92b12ce64b61.png)


![image](https://user-images.githubusercontent.com/73780930/215641914-3f19a082-a7bf-431c-9ad9-0d9ba5cc09a7.png)


When the button is pressed, it is seen that the transmission is provided on Tia Portal and we control it in this interface.
















