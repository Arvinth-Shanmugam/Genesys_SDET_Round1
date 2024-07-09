# Genesys_SDET_Round1

Step 1: 
Import the Arvinth_SDET.postman_collection.json collection to your local Postman.

Step 2:
I have created the below Collections Variables for the entire API Requests.
touser_uuid, fromUser_uuid, updated_username, message_id.

Step 3:
POST->Create user:
i had created the body name with sample username "Arvinth". Once the response has been recieved, I had extracted the "fromUser_uuid" userID of that particular person and stored in the variable.
Using Assertion, if the name contains only "Arvinth" it will pass otherwise it test will fail. 

Step 4: 
POST->Create To User:
I had created another username with the "Create To User" API request. Once the response has been recieved, I had extracted the "touser_uuid" TouserID of that particular person and stored in the variable.
Using Assertion, if the name contains only "Arvinth" it will pass otherwise it test will fail. 

Step 5:
PUT->Update User:
Using the id of the Create User[Step 3], we are modify the username with diffrent value and validating whether the updated value is coming from the response.

Step 6:
POST-> Create Message
using the id's of Create User[Step 3] and Create To User[step 4], 
