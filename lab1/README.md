# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name**: Tao Lu
**Student ID**: 41284860
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://www.youtube.com/watch?v=4PEqlEEcpos)

---

## Technical Explanations

We are using Azure as IaaS in this lab, so we put Order Service, Product Service, Store Front, and RabbitMQ all on one VM, but each one runs on a different port.

### Order Service (Node.js)

we use node.js to build backend server to handle oder, If we place order from frontend, it will send request to oder service, and then the oder service will send message to RabbitMq.

We clone the code from GitHub onto the VM. Then we install Node.js on the VM, since Order Service is written in Node.js. Once Node.js is installed, we run Order Service using `node index.js`, and keep that terminal window open so the service keeps running.

The following picture shows an order being placed.

![place order](/screenshots/Order-confirmation.png)

### Product Service (Rust)

We use Rust as the backend for Product Service. It is used to display the product IDs, names, and prices. We need to install Rust ourselves. After installing it successfully, we open another terminal and keep it running.

Once we open the Store Front page, it sends a request to Product Service and receives the product data in return. Store Front then displays all the product information to the user.

### Store Front (Vue.js)

We use the Vue framework to build the frontend page (Store Front). When the page first loads, it automatically sends a request to Product Service to get the product list. When the user clicks "Place Order," it sends a request to Order Service to submit the order.

The front page is shown below.

![frontpage](/screenshots/Frontend-page.png)

---

## Challenges and Learnings (Optional)

I used to learn how to write code, from the front end to the back end, but I rarely had a chance to learn how to actually deploy it to a server. Following this lab step by step gave me a much better understanding of how everything works together in practice.
