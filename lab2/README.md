# CST8915 Lab2: Refactoring the Lab 1 App with the 12-Factor Methodology

**Student Name**: Tao Lu
**Student ID**: 41284860
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Demo Video:

🎥[Algonquin Pet Store from Lab 1](https://www.youtube.com/watch?v=Yh-H3pPxedQ)

## Reflection Questions

1. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?

- In order to comply with Config:
  - In order-service, we changed the hard code and put the port number in the `.env` file, together with the `RABBITMQ_CONNECTION_STRING`, which contains the username and password to connect to RabbitMQ.
  - In product-service, we changed the hard code of the port number, put it in the `.env` file, and used a variable to read it.

- In order to comply with Backing Services:
  - Order-service sends order messages to RabbitMQ.
  - It seems to me that product-service did not use a backing service in this lab.

2. Why is it important to use environment variables instead of hard-coding configurations in your application?

- Because we may change the deployment environment. For example, we may change the port number, or connect to a different RabbitMQ server. We only need to change the environment variables, not the code.
- I also found that we put the RABBITMQ_CONNECTION_STRING in .env and specified `.env` in `.gitignore`, so we do not need to upload our password to GitHub.

3. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?

- Independence
  - Now the codebase becomes simpler, and we can focus on our own microservice. Besides, each team can do their job without knowing the other teams' code.
  - We can deploy each microservice independently.

- Scalability:
  - Each microservice has its own repository.It is built and deployed separately.
  - So we can scale one microservice without scaling the others. For example, if there are many orders, we can add more instances of the order-service.

## Service Repository

- [order service](https://github.com/taolucloud2/orderService)
- [product service](https://github.com/taolucloud2/productService)
- [store front](https://github.com/taolucloud2/store-front)
