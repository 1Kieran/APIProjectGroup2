# **Manitoba Polar Bear API**

## **API Description**
This API provides information about the location of polar bears in Manitoba. A requester can find a bear by listing latitude and longitude coordinates. This will return the current location and ID of the bear that is nearest to the given location using the near me endpoint. A bears  location will also be given by the ID of the bear and the date requested using the by ID endpoint. By using the list all ID endpoint the user will be returned the IDs of all polar bears currently in manitoba.

## **List of Endpoints (with parameter)**
There are three endpoints in the polar bear API
1. Show All
2. Near Me
3. By ID

### **Show All**
Show all polar bears currently in Manitoba.
```
https://manitoba.polarbear/api/showall
```
### **Near Me**

Show the polar bear closest to my location.
```
https://manitoba.polarbear/api/nearme/lat=x&lng=y
```
#### **Parameters**
1. lat(float) Latitude in decimal degrees with in the range of Manitoba. 
2. lng(float)Longitude in decimal degrees with in the range of Manitoba.
### **By ID**
 Show the whereabout of a particular bear by id and a date.
```
https://manitoba.polarbear/api/byid/id=x&date=y
```
#### **Parameters**
1. id(sting): Unique Polar Bear ID.
2. date(string): Date in YYYY-MM-DD format.
## **Description of Resources**
The bear_id refers to a single bear  
The distance refers to the distance between the bear and the current location in kilometers 
The latitude refers to the latitude  
The longitude refers to the longitude 
``` 
{
      "results":
      {
       “bear_id”:"22241”
       “distance”:"2300”
       "latitude":"65.164577"
       "longitude":"-99.264979"
      },
       "status":"OK"
}
```
## **Sample Request and Response**
Below are sample request for each of the endpoints

### **Endpoint 1**
Sample Request:
```
https://manitoba.polarbear/api/showall
```
Sample Response:
```
{
      "results":
      {

      },
       "status":"OK"
}
```
### **Endpoint 2**
Sample Request:
```
https://manitoba.polarbear/api/byid/lat=36.7201600&lng=-4.4203400&date=2022-03-17
```

Sample Response:
```
{
      "results":
      {
       "latitude":"65.164577"
       "longitude":"-99.264979"
      },
       "status":"OK"
}
```
### **Endpoint 3**
Sample Request:
```
https://manitoba.polarbear/api/nearme/bear_id=22241
```
Sample Response:
```
{
      "results":
      {
       “bear_id”:"22241”
       “distance”:"2300”
       "latitude":"65.164577"
       "longitude":"-99.264979"
      },
       "status":"OK"
}
```

**Status Codes**

The "status" field within the API response object contains the status of the request. The "status" field may contain the following values:

- "OK": indicates that the call to the API was successful;
- "INVALID_REQUEST": indicates that either lat or lng parameters are missing or invalid;
- "INVALID_DATE": indicates that date parameter is missing or invalid;
- "INVALID_ID": indicates that identification number parameter is missing or invalid;
- "UNKNOWN_ERROR": indicates that the request could not be processed due to a server error. The request may succeed if you try again.
