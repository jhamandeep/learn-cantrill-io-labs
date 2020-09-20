# Advanced Demo - Web Identity Federation  

In this advanced demo series you will be implementing a simple serverless application which uses Web Identity Federation.    
The application runs using the following technologies  

- S3 for front-end application hosting  
- Google API Project as an ID Provider  
- Cognito and IAM Roles to swap Google Token for AWS credentials  

The application runs from a browser, gets the user to login using a Google ID and then loads all images from a private S3 bucket into a browser using presignedURLs.  

This advanced demo consists of 6 stages :-  

- STAGE 1 : Provision the environment and review tasks   
- STAGE 2 : Create Google API Project & Client ID  
- STAGE 3 : Create Cognito Identity Pool  
- STAGE 4 : Update App Bucket & Test Application **<= THIS STAGE**  
- STAGE 5 : Cleanup the account  

![Stage4 - PNG](https://github.com/acantril/learn-cantrill-io-labs/blob/master/aws-cognito-web-identity-federation/02_LABINSTRUCTIONS/ARCHITECTURE-STAGE4.png)  


# STAGE 4A - Download index.html and scripts.js from the S3   

Move to the S3 Console https://s3.console.aws.amazon.com/s3/home?region=us-east-1    
Open the `webidf-appbucket-` bucket   
select `index.html` and click `Download` & save the file locally  
select `scripts.js` and click `Download` & save the file locally  

# STAGE 4B - Update files with your specific connection information  

Open the local copy of `index.html` in a code editor.    
Locate the `XXXXXXXXXX-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.apps.googleusercontent.com` placeholder   
Replace this with YOUR CLIENT ID  
Save `index.html`  

Open the local copy of `scripts.js` in a code editor.   
Locate the IdentityPoolId: `IdentityPoolId: 'XX-XXXX-X:XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX'` placeholder    
Replace the `XXXXX` part with your IDENTITY POOL ID you noted down in the previous step  
Locate the `Bucket: "REPLACE_ME_PRIVATE_PATCHES_BUCKET" ` placeholder.  
Replace `REPLACE_ME_PRIVATE_PATCHES_BUCKET` with with bucket name of the `webidf-patchesprivatebucket-` bucket
Save `scripts.js`  

# STAGE 4C - Upload files

Back on the S3 console, inside the `webidf-appbucket-` bucket.   
Click `Upload`    
Add the `index.html` and `scripts.js` files and click `Upload`    

# STAGE 4C - Test application  

Open the S3 bucket static hosting endpoint which you noted down earlier.
it should show a simple webpage



# STAGE 4 - FINISH  

- template front end app bucket
- Configured Google API Project
- Credentials to access it
- Cognito ID Pool
- IAM Roles for the ID Pool




