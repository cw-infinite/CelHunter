## Goals

### R&D AWS Goal 1
- [x] Core Serverless Services
- [ ] Basic Logic with Lambda and API Gateway
- [ ] Data Storage with DynamoDB
- [ ] Authentication with Cognito
- [ ] S3, CloundFront, and Route 53 CD

#### API Gateway
* Issue [#5](https://github.com/cw-infinite/Cellhunter/issues/5) Intro
- Connect FE and BE. [API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html)
- API Key with calls and custom domain (for other developers to use) 
- AWS Permissions (IAM) Identity and Access management. [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)
- [API End point full life cycle](https://github.com/cw-infinite/Cellhunter/blob/master/ScratchWork/fullcycle.md)
* Issue [#5](https://github.com/cw-infinite/Cellhunter/issues/5) [0.5/5]
- Body mapping template
  - extract data from Lambda only for processing,
  - this is where Ingegration Request comes in so we can use them to map, incase of the reuqst, the data pass to the action and in the case of response, the data get out of the action
  - Request body passthorught: when there are no tempaltes defined.
    - the body will not be forwareded by default anymore.
```
{
  "body-json": $input.json('$')
  ## for using event.age in lambda
  "age" : $input.json('$.personData.age')  
}
```
