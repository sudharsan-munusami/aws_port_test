Goal:
Create a flask app that displays the contents present in a aws s3 bucket  

Procedure:  

1. Create S3 bucket empid-bucketname (Please ensure not to open the bucket to public)  
    
![image](https://user-images.githubusercontent.com/82586609/115119072-4251de00-9fc4-11eb-8b55-3368a9c10939.png)
  
2. Create three folders inside bucket (A,B,C)  
  
![image](https://user-images.githubusercontent.com/82586609/115119112-66adba80-9fc4-11eb-89cd-4e9fc3f79024.png)
  
3. Put in files inside each of the folders  
    Created dummy read_me files named "foldername_Readme.txt"  
    The contents contain: "Readme file from Foldername"  
   
![image](https://user-images.githubusercontent.com/82586609/115119186-b3919100-9fc4-11eb-8d2a-81cd0ce0ff62.png)
  
4. Create a flask app that gets the folder name and lists the filename present in the corresponding folder. (Use Boto3 for reading the contents of the folder) and test the code in local  
    
    4a. Make the relevant codes in github  
    ![image](https://user-images.githubusercontent.com/82586609/115119273-2bf85200-9fc5-11eb-8ce7-29b2515b866d.png)  
    
    4b.To run the code in local, open an Ubuntu terminal and follow the below steps:  
        4b-1: Clone into the github branch (SUDSM_HARTFORD_ASSIGNMENT1)  
        4b-2: Open and activate a virtual environment (name:htassign)  
        4b-3: Instal the requirements file  
        4b-4: Install awscli and configure using the s3 access ID and Key  
        4b-5: Run the application using python app.py  
  
        ![image](https://user-images.githubusercontent.com/82586609/115119361-93160680-9fc5-11eb-99ab-f3925441f530.png)  
  
        ![image](https://user-images.githubusercontent.com/82586609/115119367-a0cb8c00-9fc5-11eb-8050-5dcf67bd17d6.png)  
  
        ![image](https://user-images.githubusercontent.com/82586609/115119439-fa33bb00-9fc5-11eb-93c4-b27057a909c8.png)  
  
    The website is now deployed from local environment as shown below:  
    ![image](https://user-images.githubusercontent.com/82586609/115119488-35ce8500-9fc6-11eb-836d-5718dc879cf6.png)  
  
    Add '/storage' to access the below page:  
    ![image](https://user-images.githubusercontent.com/82586609/115119507-4ed73600-9fc6-11eb-8dfd-630dfe12475a.png)  
  
    As could be seen, the page lists all the files present in the S3 bucket. They could also be downloaded from there. In addition, we can use the upload option to upload new files without loggin into the aws consolde. The files uploaded here would be reflected in the S3 console.  
    
    
-----Deploying the app from EC2 instance  

5. Open an EC2 instance with t2.micro in the same region as S3 console (i.e., Mumbai)  
    ![image](https://user-images.githubusercontent.com/82586609/115119586-ce650500-9fc6-11eb-99af-8dff52766e23.png)  
  
    IAM users are tagged to this instance with appropriate roles  
  
6. The security group of the instance is configured as below (allowing through port:8085)  
    Note: Similarly, the app.py needs to be configured to allow only port 8085 (unlike the case in local execution)  
    ![image](https://user-images.githubusercontent.com/82586609/115119620-02d8c100-9fc7-11eb-9c65-286779d30d55.png)  
  
7. Running the Flask app from EC2 instance:  
    7a: SSH into the EC2 instance from windows Powershell (using the .pem file, before doing so the permissions are altered as needed)  
    7b: The remaining steps are same as local execution (git clone, virtual environment, installing necessary packages, aws confiigure, deploying the app), as shown below:  
    ![image](https://user-images.githubusercontent.com/82586609/115119716-724eb080-9fc7-11eb-829b-53a0b6770365.png)  
    ![image](https://user-images.githubusercontent.com/82586609/115119806-e4bf9080-9fc7-11eb-917f-8c42e5b7d51b.png)  
      
    7c: Once done, the site can be accessed from the EC2 public url (NOTE: THE EC2 INSTANCE IS CURRENTLY STOPPED, SO IT MAY NOT BE ACCESSIBLE. PING ME TO ACTIVATE THE LINK)  
    ![image](https://user-images.githubusercontent.com/82586609/115119847-19cbe300-9fc8-11eb-992d-742d0c8bd89e.png)  
    ![image](https://user-images.githubusercontent.com/82586609/115119852-1f292d80-9fc8-11eb-9e77-994e11a45015.png)  
      
The contents of the S# buckets are now listed in the website hosted through EC2 public URL(through port 8085). In additon, the files could be modified (added, downloaded) using the app.  
  
Additional info:  
Budget set for the project:  
![image](https://user-images.githubusercontent.com/82586609/115120043-f2c1e100-9fc8-11eb-9f5a-560a20b440f7.png)  
  
Billing information post completion:  
![image](https://user-images.githubusercontent.com/82586609/115120074-26047000-9fc9-11eb-89fa-a229bbc7480f.png)  
  
NOTE:  
URL OF THE DEPLOYED APP:   
Home: http://13.234.20.181:8085/  
Storage page: http://13.234.20.181:8085/storage  
NOTE: THE EC@ INSTANCE HAS BEEN STOPPED. HENCE, THE ABOVE LINKS WON'T WORK. PING ME IF ACCESS TO WEBSITE IS NEEDED.  
  
This branch is pushed into a separate PR. Kindly propose any changes there.  
   
#SUS_Sudharsan_Munusami
