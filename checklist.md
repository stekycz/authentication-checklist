# Authentication Checklist

## Basics

1. How will the user log in?
    1. Username & password
    2. One time password/token
        1. How the user get the token/password? How is the user authenticated? (E.g. sent to verified email address)
    3. What third parties we want to support? (Google, Facebook, GitHub, ...)
2. How does the user change his/her password?
    1. Logged-in user in its profile
    2. Forgotten password
        1. How is the user authenticated to request the change?
        2. How is the user authenticated to actually change the password?
3. Do we want to support Single Sign-On (SSO)?
    1. If so, what systems are involved?
    2. Who and how manages adding/removing involved systems?
4. Do we want to support 2FA/MFA?
    1. If so, would it be required for everyone?
    2. When and how does the user set it up?
    3. How can the user cancel it?
    4. How can a user recover the account when the device/keys are lost?
5. How can the user logout?
    1. How does it work for the current session?
    2. How does it work for another sessions (on another device)?
6. How long is expiration of the sessions?
    1. Does it expire after web browser tab closing?
    2. Is the expiration prolonged after each action in the app?

## User management

1. How will the user registration work?
    1. Will the user use self-registration?
    2. Will the user automatically register after an action (eg. place an order, write a comment)?
    3. Do we want to manually register users by already existing (and logged-in) user?
    4. Do we want to manually register users by administrator of the system?
    5. When and how does the user set the first password if we allow username and password login?
2. When does the user give a consent (eg. terms of use, privacy policy)?
    1. How and when does the user give a new consent when conditions change and the new consent is needed?
    2. Can the user use the system without giving a consent? To what extent? And how long?
    3. How is it different for a user who given consent before but did not for changed conditions?
3. Is it necessary to activate an account/validate an email address?
    1. Why? What is it good for?
    2. If yes, when and how is it done?
    3. Can the user use the system without confirmation? To what extent? And how long?
    4. How do we authenticate users to activate an account/confirm an email address?
    5. How does the user request the activation of the account/confirmation of the email address again if the information for activation/validation has not been received?
    5. What will happen when the user changes email address?
4. How can a user cancel or delete their account?
    1. How does it differ if the user asks for deletion under the GDPR?
5. How do we manage authentication-related emails?
    1. How do we manage the design?
    2. How do we manage the wording?
    3. How do we address email localization?
6. Authorization
    1. Who, where and how defines the authorization rules?
    2. Who, where, and how manages authorization rules relations to users?

## OAuth 2.0/OpenID

1. How does registering a new client work?
2. How does deactivating/deleting a client work?
    1. What are the implications for existing users related to the client?
    2. What happens to users logged-in to the client?
3. How are authorization rules for clients managed?
    1. Who, when and how defines client authorization rules?
    2. What rules are automatically approved after client registration?
4. How the client requests changes in approved client authorization rules?
    1. How does it differ for the registration and for the following changes?
    2. How does it affect existing users?
    3. How does it differ for removing rules and adding rules?
5. Do we want to support the possibility for each client to have multiple sub-clients (eg. iOS, Android, Web)?
    1. If so, what are their limitations?
    2. How does it change from the main client?
6. How and where the user denies access to previously approved clients?
7. How and where the user revokes individual "sessions" within one client?
8. How long is the expiration for tokens?
    1. Access token
    2. Refresh token
    3. Authentication code
9. Do we want to use Json Web Tokens (JWT)?
    1. What implications (positive and negative) does it have to the rest of the system?
