---
Date: 2022-02-06
Author: Jimmy Briggs <jimmy.briggs@jimbrig.com>
Source: hypothesis
Link: https://cloud.google.com/blog/topics/developers-practitioners/microservices-architecture-google-cloud
Tags: ["#Type/Highlight/Article"]
Aliases: ["Microservices Architecture on Google Cloud | Google Cloud Blog", "Microservices Architecture on Google Cloud | Google Cloud Blog"]
---
# Microservices Architecture on Google Cloud | Google Cloud Blog

## Metadata
- Author: [[cloud.google.com]]
- Full Title: Microservices Architecture on Google Cloud | Google Cloud Blog
- Category: #Type/Highlight/Article
- URL: https://cloud.google.com/blog/topics/developers-practitioners/microservices-architecture-google-cloud

## Highlights
- What is microservices architecture?Microservices architecture (often shortened to microservices) refers to an architectural style for developing applications. Microservices enable you to break down a large application into smaller independent services, with each service having its own realm of responsibility. To serve a single user request, a microservices-based application can call on many individual microservices to compose its response.Containers are well-suited to microservices, since they let you focus on developing the services without worrying about dependencies. Modern cloud-native applications are usually built as microservices using containers. When you use Google Cloud, you can easily deploy microservices using either the managed container service, Google Kubernetes Engine (GKE), or the fully managed serverless offering, Cloud Run. Depending on your use case, Cloud SQL and other Google Cloud products and services can be integrated to support your microservices architecture.
- Microservices use cases Let’s consider a scenario in which you are migrating a monolithic web application or developing a new one with a microservices architecture. Microservices architectures are often event-driven with the pub/sub model, where one service publishes events and other services subscribe to the events and take action on them. In this example scenario there are four services: Order, Packaging, Shipping, and Notification:When a user places an order on the website, the Order service receives the order, does some preliminary processing, and sends the event to Google Pub/Sub. The Packaging and Notification services, which are subscribed to the events from the Order service, start the packaging process for the order and send an email notification to the customer respectively. The Packaging service sends an order packaging event to Pub/Sub. The Shipping service, which has subscribed to these events, processes shipping and sends an event to Pub/Sub. The Notification service consumes this event and sends another message to the customer with order shipment info.
- Of course, there are multiple different ways of deploying a website like this. Choosing the best option will depend on your team's specific requirements and preferences. Notice that in the example the Notification service uses Cloud Functions to run the logic for sending notifications and uses a Firestore database to look up user email addresses. The Shipping and Order services are deployed on Cloud Run while the Packaging service is deployed on GKE. They all are connecting to a Cloud SQL database.
- Some other microservices use cases include: Media content: Using a microservices architecture, images and video assets can be stored in a scalable object storage system and served directly to web or mobile apps.Transactions and invoices: Payment processing and ordering can be separated as independent services, so payments continue to be accepted even if there is a service disruption with invoicing.Data processing: A microservices platform can extend cloud support for existing modular data processing.