# Genesys_SDET_Round1

Note: For Step12 and Step13 i have noticed some bug and mentioned below.

Step 1: 
Import the perrys-summer-camp.postman_collection.json collection to your local Postman.

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
Using the id's of Create User[Step 3] and Create To User[step 4], we will extract the message id and store it in "message_id" variable.

Step 7:
POST->Create Reply Message
I had additionally created one Message using the id's of Create user [Step 3] and Create To User[step 4].

Step 8:
Get-> Get User
Using the "fromUser_uuid" variable, we will get the particular id's username Details.

Step 9:
Get-> Get Message
Using the "message_id" variable, we will get the from and to user's message Details.

Step 10:
Get-> List Users
We will get all the user names and id's which are created using step 3 and step 4 API request. Using Assertion, if the user list contains array it will pass otherwise it test will fail. 

Step 11:
Get-> List Messages
We will get all the message conversations between the fromuser and touser. Using Assertion, if the list messages contains array it will pass otherwise it test will fail. 

Step 12:
Delete->delete user
Using the userid or touserid, we can remove the user from the database.
Note: "Once we send the delete request the data is removed from the database but still the API is getting load for a longer time"- It is a Bug.

Step 13:
Delete->delete Message
Using the Message ID, we can remove the message from the database.
Note: "Once we delete the message we are getting 204 no content statuscode instead of 200"- It is a bug
