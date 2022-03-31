## **Manitoba Polar Bear API**

### **API Description**
This API provides information about the location of polar bears in Manitoba. A requester can find bear by listing latitude and longitude coordinates. This will return the current location of and ID of the bear that is nearest to the given location using the near me endpoint. A bears current location will also be given by the ID of the bear using the by id endpoint. By using the list all id endpoint the user will be returned the ids of all polar bears currently in manitoba.

### **List of Endpoints (with parameter)**

 ## Parameters
1. lat(float)Latitude in decimal degrees. 
2. lng(float)Longitude in decimal degrees.
3. id(sting): Polar Bear ID
4. date(string):Date in YYYY-MM-DD format.

## Endpoints
1. Show all polar bears in Manitoba.
 * https://manitoba.polarbear/api/showall
2. Show the polar bear closest to my location.
 * https://manitoba.polarbear/api/nearme/lat/lng
3. Show the whereabout of a particular bear.
 * https://manitoba.polarbear/api/byid/id/date

### **Description of Resources**

### **Sample Request and Response**

Sample Request

https://api.mb-polarbear.org/json?lat=36.7201600&lng=-4.4203400

https://api.mb-polarbear.org/json?lat=36.7201600&lng=-4.4203400&date=today

https://api.mb-polarbear.org/json?lat=36.7201600&lng=-4.4203400&date=2022-03-17

https://api.mb-polarbear.org/json?lat=36.7201600&lng=-4.4203400&formatted=0


sample response:

{
      "results":
      {
       “bear_id”:"22241”
       “distance”:"2300 KM”
      },
       "status":"OK"
    }
