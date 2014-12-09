# OAuth2 and Security

The Sycamore Education API is designed to offer access to the underlying data within our system while also maintaining security and guarding against undesirable access.

## OAuth2
The Sycamore School API uses the OAuth2 standard for authenticating users to use our data. The main concerns that the OAuth protocols alleviates is the role of the "3rd party" accessing a users data on their behalf. Access to a "resource" is only allowed if a request is accompanied by an 'access token'. Each token can have many different 'scopes' or permissions attached to them.  Each token is also tied to your user ID, school ID, family ID and/or studentID. Because Sycamore also has a fully developed permissions system baked into our application, only certain types of users can create tokens with certain scopes. If you would like to know more about OAuth2 in general, this link provides a great overview.

## Creating a Token
OAuth solves a great problem by providing a mechanism for 3rd parties to access protected resources on behalf of a Sycamore user, but we can also use OAuth as a user of Sycamore directly without going through a 3rd party. Inside of the system, under the "My Organizer" feature, there is a menu item called "Applications". This screen gives you the ability to create and manage access tokens. At any time you can revoke an access token for a 3rd party or create a new token for your personal use. There is also an 'Applications' tab where you can create "3rd party" apps that can access other users data in Sycamore on their behalf.

<img src="http://api.sycamoresupport.com/userfiles/529/2232/ckfinder/images/Sycamore%20OAuth%20Management.png">

## Using your token
As part of the OAuth2 standard, all requests to the API must have an "Authorization" header added with a type of "bearer". The text of the access token should follow a space after the word "bearer". However, to make this a little bit easier Sycamore has developed a "OAuth Sandbox" to test out access tokens and responses. You can visit the Sandbox here. You may also use other 3rd party OAuth testing sites like this one from Google.

<img src="http://api.sycamoresupport.com/userfiles/529/2232/ckfinder/images/OAuth%20Sandbox.png">

## Creating an Application
If you want to create an application that can access a users information on their behalf, you need to register your application with Sycamore to obtain your API key and secret. The key and secret are credentials that are given out to applications that are unique and help identify requests to the OAuth server. To create an application, you will first have to sign up for a Developer Account. Head over to https://app.sycamoreeducation.com/developer/ and click the 'Register' button. An email will be sent to you afterwords with a temporary password. Once you visit the Developer Portal and change your password to something more secure, click on the 'Applications' link on the left hand side and then the 'Register New Application' button in the upper right hand corner. A pop-up window will appear that will allow you to fill out the details about your application.

<img src="http://api.sycamoresupport.com/userfiles/529/2232/ckfinder/images/editapplications(1).jpg?dc=201411032240-132">

## Application Details
Below is a run down of the information each application will be required to enter:

| Field | Description |
|--------------------|
| App Name | The name that you've given your application. It must be unique among ALL applications (not just your own, all other Sycamore Developers). It must also follow the Brand Guidelines found here.
| Description |	a short description about what your application does. This will be viewable by the user before they authorize your application to view their information. Make it count!
| Website |	A general marketing website that users can visit to get more information about your application.
| Callback URIs | In order to make OAuth secure, our database needs to know which sites will be trying to authenticate users. When you register an application, you must tell us which URIs (or URLs) you're going to be using. URIs must start with http:// or https://. If using a local development environment, use http://localhost or https://127.0.0.1 instead. You can add multiple URIs by placing each one on it's own line.

As soon as you submit your applications information, the 'Client ID' and 'Client Secret' will be populated with values. These values are unique to your application. Please keep the Client Secret private. Treat it like a password. If it is released publically, other developers can make potentially malicious requests to our API acting as your application.

The 'Authorize URL Builder' is a simple tool that can help developers new to OAuth build the some-what-intimidating authoriz URL that supplies the OAuth server all the information that is needed to make a valid request. The URL that is built is not saved since the scopes requests must be sent via the applications code.
Scope

The scope of an access token is essentially it's permissions. "What can this access token view and what can it not view." Sycamore's OAuth scopes are almost directly tied to our in-house permission system. The list of current scopes are:

- open
- general
- individual
- classes
- families
- superuser

Some endpoints require the access token to have certain scopes and you must have the correct permission within Sycamore School before granting the token a certain scope. Your application can request any combination of scopes that you feel it requires, but please be aware that this may limit the number of users who can use your application. For example, if your application requires the 'superuser' scope, the only people that can use your application are Sycamore's superusers (~2 per school) versus an application that is usable by parents (hundreds of thousands of potential users).


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
