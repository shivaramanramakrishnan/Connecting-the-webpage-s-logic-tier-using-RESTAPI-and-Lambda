<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# APIs with Lambda + API Gateway

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-api)

**Author:** SHIVARAMAN RAMAKRISHNAN  
**Email:** shivaraman.r02@gmail.com

---

![Image](http://learn.nextwork.org/motivated_lavender_quiet_boto/uploads/aws-compute-api_c9d0e1f2)

---

## Introducing Today's Project!

Now we will see how to set up the logic tier of a 3 tier web application, the API setup using Amazon API Gateway and Lambda. We are doing this to learn how APIs work and setup the 2nd layer for our web page

### Tools and concepts

We used Lambda to set up a nodejs script which will fetch data from the yet to create DynamoDB table and we used API Gateway to create a RESTAPI which will act as a gateway for the lambda to fetch the records whenever requested.

### Project reflection

Not long

Welcome

---

## Lambda functions

AWS Lambda is a service that lets you run code without needing to manage any computers/servers - Lambda will manage them for you.

Lambda runs your code only when you need it to (so you're not paying for any idle time).

It also scales automatically, from a few requests per day to thousands per second - all you need to do is supply your code in one of the languages that Lambda supports.

The code that we have added to the function will fetch the user data based on a userid and returns that data. If it is missing, it will also shoot up an error message.

The code picks it from a DynamoDB table, which we will setup soon

![Image](http://learn.nextwork.org/motivated_lavender_quiet_boto/uploads/aws-compute-api_a1b2c3d5)

---

## API Gateway

API is a way for different software systems to talk to each other. It's like a messenger that carries requests and responses between systems.
The different types are REST, HTTP, Websocket. Whether it’s maintaining a standard web API (REST), providing real-time capabilities (WebSocket), or routing requests (HTTP).

What is Amazon API Gateway?
Amazon API Gateway is an AWS service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

API Gateway acts as the "front door" to our Lambda function. It receives requests and then forwards them to Lambda functions for processing.

Lambda processes the request, then sends the response through the API Gateway back to the user. It adds authentication and security to the request rather than directly exposing the lambda to data.

API Gateway acts as the "front door" to our Lambda function. It receives requests and then forwards them to Lambda functions for processing.

Lambda processes the request, then sends the response through the API Gateway back to the user.



![Image](http://learn.nextwork.org/motivated_lavender_quiet_boto/uploads/aws-compute-api_m3n4o5p6)

---

## API Resources and Methods

API resources are individual endpoints within your API that handle different parts of its functionality.

For example, an API for a messaging app might have separate resources for retrieving messages and for retrieving user profiles.

API methods define the actions you can perform on a resource.

They are based on standard HTTP methods, which are different commands that let you interact with data over the internet. For example:
GET to retrieve,
POST to add,
PUT to update, and
DELETE to remove data.

We have set up a GET method that wil retrive data for the lambda function. when the GET method for the /users resource is called, API Gateway will pass that request to the Lambda function you set up. When the function runs, Lambda will retrieve user data in a DynamoDB table. 

![Image](http://learn.nextwork.org/motivated_lavender_quiet_boto/uploads/aws-compute-api_c9d0e1f2)

---

## API Deployment

API Gateway lets you deploy different versions of your API to different stages. This way, you can easily control who accesses what version of your API and when.

Usually, developers work on new features or changes in a development stage of the API, test new features in the testing stage, then deploy in in the production stage.

Now we will deploy it in production

To visit the API, we copied the invoke URL and launched it in a new page, which showed an error. This is because we havent set up our DynamoDB table yet. 

![Image](http://learn.nextwork.org/motivated_lavender_quiet_boto/uploads/aws-compute-api_3ethryj2)

---

## API Documentation

For my project's extension, I am writing API documentation because it contains a detailed description of the API's functionality, including its end points (users), methods(get), parameters and responses. 

Good documentation is crucial for developers to undertand how to use the API correctly.

Once I prepared my documentation, I can publish it to the production stage set earlier and specify what version it is. 
Selecting a stage when publishing documentation makes sure that your documentation is consistent with the API version deployed to that stage.

This means you can write different versions of documentation across different stages of your API lifecycle, such as development, testing, and production.

Now we can can see metadata like our API's version and title, resources (/users), and methods (like GET) you can perform on these endpoints.

The main difference between the automatically generated documentation and the manually written part in our API is the level of customization and specificity in each section. In our written documentation, we can address specific questions, add insights, or guide the user through the API’s functionality in a more user-friendly way.

![Image](http://learn.nextwork.org/motivated_lavender_quiet_boto/uploads/aws-compute-api_z9a0b1c2)

---

---
