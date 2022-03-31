## **Manitoba Polar Bear API**

### **API Description**
This API provides information about the location of polar bears in Manitoba. A requester can find a bear by listing latitude and longitude coordinates. This will return the current location and ID of the bear that is nearest to the given location using the near me endpoint. A bears current location will also be given by the ID of the bear using the by ID endpoint. By using the list all ID endpoint the user will be returned the IDs of all polar bears currently in manitoba.

### **List of Endpoints (with parameter)**

#### **Parameters**
1. lat(float)Latitude in decimal degrees. 
2. lng(float)Longitude in decimal degrees.
3. id(sting): Polar Bear ID
4. date(string):Date in YYYY-MM-DD format.

#### **Endpoints**
1. Show all polar bears in Manitoba.
 * https://manitoba.polarbear/api/showall
2. Show the polar bear closest to my location.
 * https://manitoba.polarbear/api/nearme/lat/lng
3. Show the whereabout of a particular bear.
 * https://manitoba.polarbear/api/byid/id/date

### **Description of Resources**
The bear_id refers to a single bear  
The distance refers to the distance between the bear and the current location  
The lantitude refers to the lantitude  
The longitude refers to the longitude  
{
      "results":
      {
       “bear_id”:"22241”
       “distance”:"2300 KM”
       "lantitude":"65.164577"
       "longitude":"-99.264979"
      },
       "status":"OK"
}

### **Sample Request and Response**

Sample Request

https://api.mb-polarbear.org/json?lat=36.7201600&lng=-4.4203400

https://api.mb-polarbear.org/json?lat=36.7201600&lng=-4.4203400&date=2022-03-17


sample response:

{
      "results":
      {
       “bear_id”:"22241”
       “distance”:"2300 KM”
       "lantitude":"65.164577"
       "longitude":"-99.264979"
      },
       "status":"OK"
}



**Status Codes**

The "status" field within the API response object contains the status of the request. The "status" field may contain the following values:

- "OK": indicates that the call to the API was successful;
- "INVALID_REQUEST": indicates that either lat or lng parameters are missing or invalid;
- "INVALID_DATE": indicates that date parameter is missing or invalid;
- "INVALID_ID": indicates that identification number parameter is missing or invalid;
- "UNKNOWN_ERROR": indicates that the request could not be processed due to a server error. The request may succeed if you try again.
