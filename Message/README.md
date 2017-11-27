**Owlorbit API v1.0**
----

Message related endpoints.


- [List Messages](#list-messages)
- [Send Message](#send-message)

## List Messages

* **Description:**
  
  Get all messages in room.  Get roomId through <a href="../Room/README.md#get-all-rooms-in-domain">Room Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/message/view>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `roomId` - int <br/>
  * `pageIndex` - int <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String

  PageIndex starts at 0 and returns the next 25 messages

* **Success Response:**

   **Content:** `{'message' : string,
        'messages' : [  message { id : int, first_name : string, last_name : string, user_id : int, date_in_utc : string, message : string, avatar : string, room_id : int }... ] }`

  Contains an array of `messages`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    


## Send Message

* **Description:**
  
  Send message in room.  Get roomId through <a href="../Room/README.md#get-all-rooms-in-domain">Room Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/message/send>

* **Method:**

  * `POST`

* **Data Params:**

  * `roomId` - int <br/>
  * `message` - String <br/>  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String

* **Success Response:**

   **Content:** `{'message' : string, 'message_id' => int}`

  Contains a success message.

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}` 