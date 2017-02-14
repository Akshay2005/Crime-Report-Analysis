# Crime-Report-Analysis

A simple RPC application in order to check crime report of a location. Analyze the raw data and infer valuable information like most dangerous streets, crime types, etc.
Built using Spyne - Python RPC Toolkit

#### Input (HttpRpc)

* lat - latitude of a location
* lon - longitude of a location
* radius - radius distance in miles.


```sh
curl "http://localhost:8000/checkcrime?lat=37.334164&lon=-121.884301&radius=0.02"
```

#### Output (Json)

```json
{
    "total_crime" : 24,
    "the_most_dangerous_streets" : [ "E SANTA CLARA ST", "E SAN FERNANDO ST" , "N 11TH ST" ],
    "crime_type_count" : {
        "Assault" : 10,
        "Arrest" : 8,
        "Burglary" : 6,
        "Robbery" : 4,
        "Theft" : 2,
        "Other" : 1
    },
    "event_time_count" : {
        "12:01am-3am" : 5,
        "3:01am-6am" : 0,
        "6:01am-9am" : 1,
        "9:01am-12noon" : 2,
        "12:01pm-3pm" : 2,
        "3:01pm-6pm" : 1,
        "6:01pm-9pm" : 0,
        "9:01pm-12midnight" : 9
    } 
}
```

> the_most_dangerous_streets: Top 3 streets only. It can be less than 3 streets if a location doesn't have enough crime.
