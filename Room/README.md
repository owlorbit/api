**Owlorbit API v1.0**
----

Room related endpoints.


- [Get All Rooms in Domain](#get-all-rooms-in-domain)
- [Get All Rooms for User](#get-all-rooms-for-user)
- [Join Room](#join-room)
- [Create Room](#create-room)

## Get All Rooms in Domain

* **Description:**
  
  Get all rooms in domain

* **URL**

  <https://api.owlorbit.com/v1/room/get_rooms_in_domain>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'rooms' : [  room { roomId : int, name : string, last_message : string, is_public_channel : int (0,1), last_display_name : string }... ] }`

  Contains an array of `rooms`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    


## Get All Rooms for User

* **Description:**
  
  Get all rooms for user by email

* **URL**

  <https://api.owlorbit.com/v1/room/get_rooms_by_email>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `email` - String <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'rooms' : [  room { roomId : int, name : string, last_message : string, is_public_channel : int (0,1), last_display_name : string }... ] }`

  Contains an array of `rooms`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`  

## Join Room

* **Description:**
  
  Have User by email Join Room by email

* **URL**

  <https://api.owlorbit.com/v1/room/join_room_by_email>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `roomId` - int <br/>
  * `email` - String <br/>  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string}`

  Contains a success message.

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}` 

## Create Room

* **Description:**
  
  Create room for email

* **URL**

  <https://api.owlorbit.com/v1/room/join_room_by_email>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `userIds` - int[] <br/>
  * `email` - String <br/>  
  * `name` - String <br/>  
  * `isFriendsOnly` - int (0, 1) <br/>  
  * `isPublic` - int (0, 1) <br/>  
  * `messageTemplateId` - int (optional) <br/>  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string, 'room_id' : int}`

  Contains a success message.

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`         

