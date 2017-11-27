**Owlorbit API v1.0**
----

Group related endpoints.


- [List All Groups](#list-all-groups)
- [Create Group](#create-group)
- [Update Group](#update-group)


## List all groups

* **Description:**
  
  List all groups

* **URL**

  <https://api.owlorbit.com/v1/group/all>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string, 
    'groups' : [  group { id : int, name : string, domain_id : int, created : timestamp}... ] }`

  Contains an array of `groups`

 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`


## Create group

* **Description:**
  
  Create group.  Get `userId` through <a href="../Users/README.md#list-all-users-in-domain">User Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/group/add>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `groupName` - String <br/>
  * `usersAdded` - int[] <br/>  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string, 'groupId' : int}`  
 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`

## Update group

* **Description:**
  
  Update group.  Get `userId` through <a href="../Users/README.md#list-all-users-in-domain">User Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/group/update>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `groupId` - int <br/>  
  * `usersAdded` - int[] <br/>  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string}`  
 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`    