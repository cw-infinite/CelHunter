# Resources
* [Life Cycle](#life-cycle)
  - [Method Request](#method-request)
  - [Integration Reqeust](#integration-reqeust)
  - [Integration Response](#integration-response)
  - [Method Response](#method-response)
* [API](#api)
* [AWS Lambda](#aws-lambda)

## Life Cycle 
> Client (send request)> GET method 

| End |   |   |   |   |   | End  |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|  Client | > | Method Request  | > | Integration Reqeust | >  | V |
| A  | < | Method Requespons  | < | Integration Response  | < | Lamda   |

#### Method Request 
* **Authentication, Request Rejection body, head, Reuqest validation**
* Gate Keeper, pass to have the schema we expected to have
* GET (end point will react to GET requets being sent to this path: General URL

#### Integration Reqeust
* mapping / transforming/ extracting data ( with request body )
* trigger this end point
* transform and pass it on to action / to Lambda

#### Integration Response
* analyze and do reverse of the Integration Request
* take the data and transform that for response and set tup the response.

#### Method Response
* Just for response data/define the shape of our response
* Send Response back to users

## API

* Proxy resources : this will be catch all resources, catching all other paths and methods, flexible path therefore your api may only have single resource.
* CORS (Cross Origin Resource Sharing): Important
  * Security model wherei in generally not allowed access resource on a server from another server
  * Allow client to send subsequent reuests with headers like the content type. 
  * Allow client to sned any tpye of HTTP request: GET, POST, PUT, DELETE, etc...
  * Allow to do security from any domain which is wildcard character: Access-control-Allow-Origin: "*"
* Post : Integration type: which kinds of action do you want to execute whenever a request hits this resource
* Proxy -> take all metadata, pass unfiltered json -> Lambda


| AWS Lambda   | ➡️  | Event Source  | ➡️  | Code  | ➡️  |  Result  |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   |   | S3 (File uploaded) CloudWatch (Log/Scheduled Job) API Gateway  |   | NodeJS 10.x  |   |  Interact with other AWS to response |

## AWS Lambda
* Handler : syntaX [file name].[function name] , EX) index.js has main(), = index.main

