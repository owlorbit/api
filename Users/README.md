**Owlorbit API v1.0**
----

User related endpoints.


- [Does User Exist](#does-user-exist)
- [Add User to Domain](#add-user-to-domain)
- [List All users in Domain](#list-all-users-in-domain)


## Does User Exist

* **Description:**
  
  Checks if user exists.

* **URL**

  <https://api.owlorbit.com/v1/user/does_email_exist>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `email` - String <br/>
  * `domain` - String <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string, emailExists: bool }`
 
* **Error Response:**

    **Content:** `{ message : string, emailExists: bool, successful : bool }`



## Add User to Domain

* **Description:**
  
  Add a new user to domain.

* **URL**

  <https://api.owlorbit.com/v1/user/add_user_to_domain>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `email` - String <br/> 
  * `password` - String <br/>
  * `first_name` - String <br/>
  * `last_name` - String <br/> 
  * `phone_number` - String <br/>
  * `description` - String <br/> 
  * `domain` - String <br/>
  * `isPublic` - Int (0, 1) <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'userId' : int}`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    


## List all users in Domain

* **Description:**
  
  List all users in your domain

* **URL**

  <https://api.owlorbit.com/v1/user/list_all_domain_users>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'users' : [  user { userId: int, email : string, phone_number : string, first_name : string, last_name : string, avatar : string }... ] }`

  Contains an array of `users`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    

