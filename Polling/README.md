**Owlorbit API v1.0**
----

Polling related endpoints.


- [List All Running Polls](#list-all-running-polls)
- [Get Choices by Id](#get-choices-by-id)
- [Get Responses](#get-responses)
- [Create Poll](#create-poll)


## List all running polls

* **Description:**
  
  List all running polls

* **URL**

  <https://api.owlorbit.com/v1/polling/get_all_running>

* **Method:**

  * `POST`
  
* **Data Params:**
  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string, 
    'polls' : [  poll { id : int, user_id : int, group_id : int, question : string, manual_location_request_enabled : int (0, 1) }... ] }`

  Contains an array of `polls`

 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`

## Get Choices by Id

* **Description:**
  
  Get polling choices by polling id

* **URL**

  <https://api.owlorbit.com/v1/polling/get_choices_by_id>

* **Method:**

  * `POST`
  
* **Data Params:**
  
  * `pollingId` - int <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string, 
    'polling_choices' : [  poll { id : int, polling_id : int, choice : string }... ] }`

  Contains an array of `polling choices`

 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`


## Get Responses

* **Description:**
  
  Get responses

* **URL**

  <https://api.owlorbit.com/v1/polling/get_responses>

* **Method:**

  * `POST`
  
* **Data Params:**
  
  * `pollingChoiceId` - int <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**

    **Content:** `{ message : string, 
    'responses' : [  response { polling_id : int, polling_choice_id : int, user_id : int, first_name : string, last_name : string, email : string, avatar : string, created : timestamp }... ] }`

  Contains an array of `responses`

 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`  


## Create Poll

* **Description:**
  
  Create Poll.  Get `groupId` through <a href="../Group/README.md#list-all-groups-in-domain">Group Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/polling/create>

* **Method:**

  * `POST`
  
* **Data Params:**
  
  * `choices` - string[] <br/>
  * `question` - string <br/>
  * `groupId` - int (optional) <br/>
  * `manualLocationEnabled` - int (0, 1) <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


  -If groupId is not specified, it will send the poll to everyone in the domain.
  -manualLocationEnabled if enabled, requests if the user wants to share their location after they receive the push notification.

* **Success Response:**

    **Content:** `{ message : string, 
    'responses' : [  response { polling_id : int, polling_choice_id : int, email : string, created : timestamp }... ] }`

  Contains an array of `responses`

 
* **Error Response:**

    **Content:** `{ message : String, successful: false }`      
