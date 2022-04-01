# **Manitoba Polar Bear API**

## **API Description**
This API provides information about the location of polar bears in Manitoba. A requester can find information about a bear they are familiar with or discover new bears.

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
1. lat(float) Latitude in decimal degrees with in Manitoba. 
2. lng(float)Longitude in decimal degrees with in Manitoba.
### **By ID**
 Show the whereabout of a particular bear
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

### **Show All**
Sample Request:
```
https://manitoba.polarbear/api/showall
```
Sample Response:
```
{
      "results":
      {
       "22241": 
       { 
        "latitude":"58.059401"
        "longitude":"-93.006627" 
       }
       "22242": 
       {
        "latitude":"65.164577"
        "longitude":"-99.264979" 
        59.872335, -95.933006 
       }
       "22243": 
       {
        "latitude":"58.059401"
        "longitude":"-93.006627"
        "latitude":"58.638282"
        "longitude":"-94.995443"  
       }
      },
       "status":"OK"
}
```

### **Near Me**
Sample Request:
```
https://manitoba.polarbear/api/nearme/lat=49.810256&lng=-97.132288
```
Sample Response:
```
{
      "results":
      {
       “bear_id”:"22241”
       “distance”:"1005”
       "latitude":"58.059401"
       "longitude":"-93.006627"
      },
       "status":"OK"
}
```
### **By ID**
Sample Request:
```
https://manitoba.polarbear/api/byid/bear_id=22241&date=2022-03-17
```

Sample Response:
```
{
      "results":
      {
        "latitude":"58.059401"
        "longitude":"-93.006627"
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
