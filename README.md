# PHP K12 SSO

This is a php example of setting up an SSO (Single Sign-On) from Blackbaud onProducts.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. Please read the [SSO Tutorial](http://on-api.developer.blackbaud.com/tutorials/jwt-sso/) first.


## Local Setup
Copy the `.env.example` file to a local `.env` and ensure all the settings are correct for your local environment, 
filling in the secret keys or providing their own values when necessary.

Add your application configuration to a `.env` file in the root of your
project. **Make sure the `.env` file is added to your `.gitignore` so it is not
checked-in the code**

### Example
```shell
S3_BUCKET="dotenv"
SECRET_KEY="souper_seekret_key"
```

### Prerequisites
* Local Server running PHP
* Ability to clone or download code from Github
* Ability to create SSO in onProducts (Platform Manager role)

### Anatomy of provided JWT
Properties | Description
------------ | -------------
iat | Issued At. The time the token was generated, this is used to help ensure that a given token gets used shortly after it's generated. 
jwt | JSON Web Token ID. A unique id for the token, used to prevent token replay attacks.
exp | Expiration time of token ( 5 Minutes from iat )
nbf | Defines the time before which the JWT MUST NOT be accepted for processing ( Set to iat )
iss | The issuer of the token. ie: https://SCHOOLNAME.myschoolapp.com
aud | The audience of the token. ie: The domain of the redirect url from the SSO Settings screen.
uid | User Id from Profile
hid | Host Id from Profile
onapi | Url to get more user info. Must have API Access and valid API Token




## Built With

* [JWT](https://jwt.io/) - JSON Web Tokens
* [Composer](https://getcomposer.org/) - Dependency Manager for PHP
* [lcobucci/jwt](https://github.com/lcobucci/jwt) - A simple library to work with JSON Web Token and JSON Web Signature
