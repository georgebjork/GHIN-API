# ghin-api #

NOTE: The intention of this project is not to take advantage of GHIN and their product. It is merely as fun side project I wanted to make and to try .NET Minimal APIs. This project will not be hosted live anywhere. For larger scale projects, please reach out to GHIN for access to their API. The intention of this is to be used for small side projects for golfers to use to track stats and whatnot and what to see their offical GHIN handicap. Thank you. 

This is an API that will allow users to pull data from GHIN using their login credentials. 

I noticed when building an app called ForeScore, that there is no good way to pull in Handicap data from GHIN. This is a REST API that will attempt to help solve this issue. The API will utilize a users GHIN number and password in order to aquire data from GHIN.

This API utilizes .NET 6 new Minimal API.

## How to use ##

First you must make a post request to ` /api/login ` with your GHIN creditals as the body.

```
  {
    'ghinNum' : {your-ghin-number},
    'password' : {your-ghin-password}
  }
  
```

This will then return a webToken, indicating that you've been logged in, that will be used to make further requests.

```
{
  'webToken' : {webToken-here}
}

```
Once you have that webToken, you will then use it for all GET Requests using the same format as it was returned. 


### GET Request ###

` api/{ghinNum} `

This will return all data associated with that GHIN number.

` api/{ghinNum}/recentScores `

This will return all recent scores for the golfer.


### POST Requests ###

` api/login `

This will log the user in and return a webToken.





