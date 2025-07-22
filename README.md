# Static-Website
**Creating and Hosting a Static Website on S3**

**Step 1** 

Log into your AWS Management Console and search for S3, then click on it to open

<img width="940" height="410" alt="image" src="https://github.com/user-attachments/assets/3101ea67-798b-41d8-8cb9-31c6f8008dc8" />




**Step 2**

•	Then create a new bucket. Click on General purpose as the original bucket type since it allows you to store different objects. It is also the default and recommended type.

•	Choose a bucket name

<img width="940" height="415" alt="image" src="https://github.com/user-attachments/assets/7bdba26f-9939-4c00-803a-cdc5d19747ee" />



•	Since the bucket uses the bucket owner preferred ownership setting, enabling ACLs (Access Control Lists) will help preserve object permissions when other accounts upload files

•	Choosing the bucket owner preferred also helps the user to retain ownership of objects uploaded by other users



<img width="1031" height="456" alt="image" src="https://github.com/user-attachments/assets/c5ac72e6-bae5-4729-afa4-97f0c2f928bb" />




Turn off Block all public access to make the content of the bucket accessible to other users. Since it is a static website that is been hosted, access should be allowed to the public so that other users can access the website



<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/f4ed2975-3749-4a48-9e4f-cd987f6f0977" />


Enable Bucket Versioning to preserve, retrieve, and restore every version of every object stored in the bucket. Thus, older versions of the bucket are not deleted but just hidden



<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/85ba2eca-af63-4582-8ad1-51f6d950b712" />


Click on Create bucket

<img width="940" height="414" alt="image" src="https://github.com/user-attachments/assets/2a39d372-2b18-4779-b761-39cb3f64c224" />



**Step 3**
•	Click on the bucket name to open

•	Go to Upload

•	Choose Add files/Add folder. It could be both too depending on the content that is been uploaded



<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/a700d540-99b0-4295-bca9-4e6dce5cc00a" />


Click on Upload


<img width="940" height="417" alt="image" src="https://github.com/user-attachments/assets/dee9cdf7-94aa-4ce4-921f-bf4acc8eaf99" />


Below shows the files and folder been uploaded successfully


<img width="940" height="418" alt="image" src="https://github.com/user-attachments/assets/8769644b-d4ad-494c-a0a2-a9ebfd032a88" />



**Step 4**

**Editing Bucket Policy**

•	Open the bucket, click on Edit bucket policy

•	Click on Policy generator

<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/dbf8cbce-d566-4981-bacc-cbc0c9599f56" />


•	Choose S3 Bucket Policy as the policy type

•	Effect, Allow

•	* for the Principal

<img width="940" height="435" alt="image" src="https://github.com/user-attachments/assets/4e8ed818-b9d2-4a57-94b8-ed8e3d129985" />


•	Add Statement

•	Then hit on Generate Policy

<img width="940" height="422" alt="image" src="https://github.com/user-attachments/assets/d8af1fe3-3f09-42f5-aada-52694d5f4ced" />


The below image shows the JSON Policy Document generated. Copy the policy

<img width="940" height="445" alt="image" src="https://github.com/user-attachments/assets/05d16f79-2ed1-4424-90c1-d9ec5a9bb3b0" />



•	Go back to Bucket policy and click on Add a new statement. 

•	Paste the copied JSON Policy into the blank space

•	Add a slash (/) and asterisk (*) to the bucket arn

•	Click on save changes

<img width="940" height="414" alt="image" src="https://github.com/user-attachments/assets/472cec02-4326-42ef-ba17-5fd0cff7806d" />



Below shows the bucket policy been successfully edited


<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/09d8abe8-1bc2-4b6c-bb87-95e1ac95a746" />


**Step 5**

**Enabling Static Website Hosting**

•	From the bucket Properties tab, move to Static website hosting and click on Edit

•	This is to enable S3 static website hosting 


<img width="940" height="414" alt="image" src="https://github.com/user-attachments/assets/29cc1d6c-deef-41fc-9d9a-6ddfa4ea3a16" />


Choose Enable for Static website hosting and leave the rest at default

<img width="940" height="418" alt="image" src="https://github.com/user-attachments/assets/9b609076-d337-4bcc-acef-17b8661f9a58" />


Retype the names that appear in the boxes provided. In this case, index.html and error.html

<img width="940" height="412" alt="image" src="https://github.com/user-attachments/assets/84aa5e87-c7b3-4aa0-bbb4-8647f919a267" />


Click on Save changes

<img width="940" height="417" alt="image" src="https://github.com/user-attachments/assets/1424da38-302d-40af-81d1-f2c56ce7ad00" />


The below image shows the successful edit of static website hosting


<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/3da825c8-0554-4917-8d0e-c7025dc7adfe" />



**Step 6**

**Verify access to the website**

To view the content of the website, go to Static website hosting

Copy the Bucket website endpoint

Paste in a web browser to view the content 

<img width="940" height="416" alt="image" src="https://github.com/user-attachments/assets/94a390c8-3c8b-444d-93d6-443f194ff7a5" />


The images below display the static website on the web browser

<img width="940" height="475" alt="image" src="https://github.com/user-attachments/assets/9aeeba4a-9737-4604-9a3d-2aef852d9dc6" />


<img width="940" height="465" alt="image" src="https://github.com/user-attachments/assets/1219f476-e493-40fd-aa4f-4687c18b72d5" />


**Open the link below to view the static website**

http://fadi-staticwebsite-hosting.s3-website-us-east-1.amazonaws.com

This will only be available for a day!


**Challenge Faced**

Could not generate bucket policy because the slash and asterisk (/*) where ommited

