**Owlorbit API v1.0**
----

Meetup related endpoints.


- [Get All Meetup Points in Room](#get-all-meetup-points-in-room)
- [Get All Meetup Points by Email](#get-all-meetup-points-by-email)
- [Add Meetup Point](#add-meetup-point)
- [Update Meetup Point](#update-meetup-point)
- [Disable Meetup Point](#disable-meetup-point)

## Get All Meetup Points in Room

* **Description:**
  
  Get all Meetup Points in Room

* **URL**

  <https://api.owlorbit.com/v1/meetup/get_all>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `roomId` - int <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'meetup_locations' : [  meetup_location { id : int, user_id : int, room_id : int, title : string, subtitle : string, longitude : double, latitude : double, metadata : json, created : string, active : int (0,1) }... ] }`

  Contains an array of `meetup_locations`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    

## Get All Meetup Points by Email

* **Description:**
  
  Get all Meetup Points by Email

* **URL**

  <https://api.owlorbit.com/v1/meetup/get_all_by_email>

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
        'meetup_locations' : [  meetup_location { id : int, user_id : int, room_id : int, title : string, subtitle : string, longitude : double, latitude : double, metadata : json, created : string, active : int (0,1) }... ] }`

  Contains an array of `meetup_locations`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}` 

## Add Meetup Point

* **Description:**
  
  Add Meetup Point to Room.  If you set isGlobal to 1, all rooms will contain this meet-up

* **URL**

  <https://api.owlorbit.com/v1/meetup/add_by_email>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `email` - String <br/>
  * `title` - String <br/>
  * `subtitle` - String <br/>
  * `roomId` - int <br/>  
  * `longitude` - float <br/>    
  * `latitude` - float <br/>      
  * `metadata` - JSON (optional) <br/>  
  * `isGlobal` - int (0, 1) <br/>    
  * `subtitle` - String <br/>  
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'meetup_id' : int  }`

  
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`

## Update Meetup Point

* **Description:**
  
  Update Meetup Point to Room

* **URL**

  <https://api.owlorbit.com/v1/meetup/update_by_id>

* **Method:**

  * `POST`
  
* **Data Params:**
  
  * `meetupId` - int <br/> 
  * `longitude` - float <br/>    
  * `latitude` - float <br/>      
  * `metadata` - JSON (optional) <br/>    
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string }`

   Success message will be returned.

  
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`              


## Disable Meetup Point

* **Description:**
  
  Disable Meetup Point

* **URL**

  <https://api.owlorbit.com/v1/meetup/disable>

* **Method:**

  * `POST`
  
* **Data Params:**
  
  * `meetupId` - int <br/> 
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string }`

   Success message will be returned.

  
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`              
