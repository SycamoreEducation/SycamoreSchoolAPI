# OAuth2 and Security

The Sycamore Education API is designed to offer access to the underlying data within our system while also maintaining security and guarding against undesirable access.

## OAuth2
The Sycamore School API uses the OAuth2 standard for authenticating users to use our data. The main concerns that the OAuth protocols alleviates is the role of the "3rd party" accessing a users data on their behalf. Access to a "resource" is only allowed if a request is accompanied by an 'access token'. Each token can have many different 'scopes' or permissions attached to them.  Each token is also tied to your user ID, school ID, family ID and/or studentID. Because Sycamore also has a fully developed permissions system baked into our application, only certain types of users can create tokens with certain scopes.

## Creating a Token
OAuth solves a great problem by providing a mechanism for 3rd parties to access protected resources on behalf of a Sycamore user, but we can also use OAuth as a user of Sycamore directly without going through a 3rd party. Inside of the system, under the "My Organizer" feature, there is a menu item called "Applications". This screen gives you the ability to create and manage access tokens. At any time you can revoke an access token for a 3rd party or create a new token for your personal use. There is also an 'Applications' tab where you can create "3rd party" apps that can access other users data in Sycamore on their behalf.

<img src="http://api.sycamoresupport.com/userfiles/529/2232/ckfinder/images/Sycamore%20OAuth%20Management.png">

## Using your token
As part of the OAuth2 standard, all requests to the API must have an "Authorization" header added with a type of "bearer". The text of the access token should follow a space after the word "bearer". However, to make this a little bit easier Sycamore has developed a "OAuth Sandbox" to test out access tokens and responses. You can visit the Sandbox here. You may also use other 3rd party OAuth testing sites like this one from Google.

<img src="http://api.sycamoresupport.com/userfiles/529/2232/ckfinder/images/OAuth%20Sandbox.png">

## Endpoint Security

OAuth provides a way to secure access to the API at large, but there must be additional security to make sure only the correct endpoints work for the given user. Each endpoint contains security checkpoints to make sure only the correct users are viewing information. Below is a rundown of the checkpoints that we use:

- checkstudent - Is the student ID associated with the access token the same as the student ID being accessed?
- checkfamily - Is the family ID associated with the access token the same as the family ID being accessed?
- checkuser - Is the user ID associated with the access token the same as the user ID being accessed?
- checkclass - Does this user have access to view the information in a specific classroom?
- checkschool - Is the school ID associated with the access token the same as the school ID being accessed?
- checkteacher - Is the user trying to access this resource a teacher?

We will be adding these security checkpoints to our documentation for each endpoint.



Thoroughly confused? Awesome! Let's take a look at how the API has changed over time.
