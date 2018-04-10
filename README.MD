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

---

`https://wonderstream.net/api/v1/current/payments/` 
* `{{ GET }}` Displays currently logged in user’s payment history.

---

`https://wonderstream.net/api/v1/current/livestreams/` 
* `{{ GET }}` Displays currently logged in user’s livestreams. 

---

`https://wonderstream.net/api/v1/purchase/` 
* `{{ POST }}` Purchases a new livestream, and bills the credit card on file that belongs to the user account associated with the authentication token.
* _When creating a new livestream, you will have to also submit the email address that the token belongs to._
* _(Requires the token to match the user that is being passed. For example, if JaneDoe has the token 1234, a successful POST can only be made if the username specified is JaneDoe, with the token 1234 passed a long in the header.)_ 

---

`https://wonderstream.net/api/v1/livestreams/` 
* `{{ GET }}` Returns a list of all publically viewable livestreams. 

---

`https://wonderstream.net/api/v1/livestreams/<id>/` `{{ GET, PUT }}`
* `GET` Retrieves the details of a specific livestream.
* `PUT` Update data of a specific livestream _(Requires the token to match that of the livestream ID’s Owner)_

---

`https://wonderstream.net/api/v1/livestreams/<id>/sponsors/` `{{ GET, POST, PUT }}`
* `GET` Retrieves a list of sponsors associated with a livestream.
* `PUT` Update content of the existing sponsors _(Requires the token to match that of the livestream ID’s Owner)_
* `POST` Create a new sponsor associated with the livestream event. _(Requires the token to match that of the livestream ID’s Owner)_

---
