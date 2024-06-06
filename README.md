# Hello World Node.js App on AWS ECS with Terraform and GitHub Actions

This project demonstrates how to deploy a simple "Hello World" Node.js application to AWS ECS using Fargate, with Infrastructure as Code (IaC) using Terraform, and a CI/CD pipeline using GitHub Actions.

## Prerequisites

- [Node.js](https://nodejs.org/)
- [Docker](https://www.docker.com/get-started)
- [Terraform](https://www.terraform.io/downloads.html)
- AWS account
- GitHub account

## Application Overview

The Node.js application is a simple HTTP server that responds with "Hello World".

### `app.js`

```javascript
const http = require('http');

const hostname = '0.0.0.0';
const port = process.env.PORT || 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
###
## Final Steps
Ensure you have created the necessary secrets in your GitHub repository:

- DOCKER_USERNAME
- DOCKER_PASSWORD
- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
