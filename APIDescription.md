# **Manitoba Polar Bear API**

## **API Description**
This API provides information about the location of polar bears in Manitoba. The different endpoints can help a requester find new bears or check in on bears they already know.


## **List of Endpoints (with parameters)**
Endpoints:
1. Show All
2. Near Me
3. By ID

### **Show All**
Show all polar bears in Manitoba.
```
https://manitoba-polarbear/api/showall
```
### **Near Me**

Show the polar bear closest to my location.
```
https://manitoba-polarbear/api/nearme/lat=x&lng=y
```
Parameters:
1. lat: Latitude in decimal degrees with in Manitoba. 
2. lng: Longitude in decimal degrees with in Manitoba.
### **By ID**
Show the location of a particular bear
```
https://manitoba-polarbear/api/byid/id=x&date=y
```
Parameters:
1. id: Unique polar bear ID.
2. date: Date in YYYY-MM-DD format.  
   
## **Description of Resources**
Resources are formatted in JSON with "results" and "status" fields

### **Results**
possible return values:
* bear_id: ID for the bear
* latitude: Latitude of the bear.
* longitude: Longitude of the bear.
* distance: the number of kilometers between you and the bear
#### **Show All**
Results return an array "bears" whos entires have:
* bear_id
* latitude
* longitude

#### **Near Me**
Results:
* bear_id
* distance
* latitude
* longitude

#### **By ID**
Results:
* latitude
* longitude

### **Status Codes**
The "status" field contains the status of the request. This field may contain:
- "OK": The API call was successful.
- "INVALID_REQUEST": The lat or lng parameters are missing or invalid.
- "INVALID_DATE": The date parameter is missing or invalid.
- "INVALID_ID": the identification number is missing or invalid.
- "UNKNOWN_ERROR": The request could not be processed due to a server error. 
## **Sample Requests and Responses**
Below are sample request for the endpoints

### **Show All**
Sample Request:
```
https://manitoba-polarbear/api/showall
```
Sample Response:
```
{
      "results":
       "bears":
       [ 
         { 
          "bear_id":"22241"
          "latitude":"58.059401"
          "longitude":"-93.006627" 
         },
         {
          "bear_id: "22242"
          "latitude":"59.872335"
          "longitude":"-95.933006"  
         } 
       ]
      },
       "status":"OK"
}
```

### **Near Me**
Sample Request:
```
https://manitoba-polarbear/api/nearme/lat=49.810256&lng=-97.132288
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
https://manitoba-polarbear/api/byid/bear_id=22241&date=2022-04-01
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

