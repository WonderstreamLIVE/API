# Wonderstream API

## Overview

Wonderstream provides a robust API that allows authenticated users to retrieve and purchase livestreams. To access the API, you must have a registered Wonderstream account. If you wish to create livestreams, you will also need to have a valid credit card associated with your account.

## Authentication Methods
Wonderstream uses a simple token-based HTTP Authentication scheme. All endpoints require this token to be passed in the header. 

## Obtaining  an Authentication Token
To retrieve your unique token, you will first have to login to your Wonderstream account, then navigate to the API section in your account page (https://wonderstream.net/account/). You’ll find your first key there. If you wish to generate a new key for any reason, you can make a POST request to https://wonderstream.net/api/v1/token/ with your username and Password. A new token will be generated every time you make a valid POST. 

## API Endpoints

`https://wonderstream.net/api/v1/current/` `{{GET}}`
Displays the currently logged in user’s data. 

`https://wonderstream.net/api/v1/current/payments/` `{{ GET }}`
Displays currently logged in user’s payment history.


