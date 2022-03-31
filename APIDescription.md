## **Manitoba Polar Bear API**

### **API Description**
This API provides information about the location of polar bears in Manitoba. A requester can find bear by listing latitude and longitude coordinates. This will return the current location of and ID of the bear that is nearest to the given location using the near me endpoint. A bears current location will also be given by the ID of the bear using the by id endpoint. By using the list all id endpoint the user will be returned the ids of all polar bears currently in manitoba.
### **List of Endpoints (with parameter)**

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
