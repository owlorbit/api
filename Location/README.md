**Owlorbit API v1.0**
----

Location related endpoints.


- [List All User Locations](#list-all-user-locations)
- [List User Location by Email](#list-user-location-by-email)
- [List All Users in Room](#list-all-users-in-room)
- [Add User location](#add-user-location)


## List all user locations

* **Description:**
  
  View all users locations on map

* **URL**

  <https://api.owlorbit.com/v1/location/get_all_user_locations>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**
    
    **Content:** 

        {'message' : string, 

        'locations' : location { 

        longitude : float,

        latitude : float,

        altitude : float,

        metadata : json,

        email : string, 

        phone_number : string, 

        first_name : string,

        last_name : string,

        avatar : string } }

  Contains a `location` object    
 
* **Error Response:**

    **Content:** `{'message' : string, 'successful' : false}`    


## List User Location by Email

* **Description:**
  
  View all users location by email

* **URL**

  <https://api.owlorbit.com/v1/location/user_location_by_email>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String


* **Success Response:**
    
    **Content:** 

        {'message' : string, 

        'locations' : [  location { 

        longitude : float,

        latitude : float,

        altitude : float,

        metadata : json,

        email : string, 

        phone_number : string, 

        first_name : string,

        last_name : string,

        avatar : string }... ] }

  Contains an array of `locations`    
 
* **Error Response:**

    **Content:** `{'message' : string, 'successful' : false}`    


## List all users in Room

* **Description:**
  
  List all users and their location in specific room.  Get roomId through <a href="../Room/README.md#get-all-rooms-in-domain">Room Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/location/get_locations_by_room_id>

* **Method:**

  * `POST`
  
* **Data Params:**

  * `roomId` - Int <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string,
        'locations' : [  location { longitude : float, latitude : float, altitude : float, metadata : json, email : string, phone_number : string, first_name : string, last_name : string, avatar : string }... ] }`

  Contains an array of `location`

 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    


## Add User Location

* **Description:**
  
  Update user location.  Get `email` through <a href="../Users/README.md#list-all-users-in-domain">User Routes</a>

* **URL**

  <https://api.owlorbit.com/v1/location/add_by_user_email>

* **Method:**

  * `POST`

* **Data Params:**

  * `email` - String <br/>
  * `longitude` - Double <br/>
  * `latitude` - Double <br/>
  * `altitude` - Double (optional) <br/>
  * `metadata` - JSON (optional) <br/>
  * `publicKey` - String <br/>
  * `privateKey` - String  <br/>
  * `encryptedSession` - String <br/>
  * `sessionHash` - String



* **Success Response:**

   **Content:** `{'message' : string }`
  
 
* **Error Response:**

    **Content:** `{'message' : string,
        'successful' : false}`    
