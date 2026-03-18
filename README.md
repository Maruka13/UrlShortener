# 🌐 Serverless URL Shortener

<p align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS%20Lambda-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white" />
  <img src="https://img.shields.io/badge/Cloud--Native-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Event--Driven-FF4F8B?style=for-the-badge" />
</p>

> **Cloud-native URL shortener built with Serverless architecture**, designed for high scalability, low cost, and stateless execution.

---
 📌 This project is part of a distributed system  
 👉 See full architecture: https://github.com/Maruka13/serverless-url-shortener-architecture

## 🚀 Overview

This project is a **Serverless microservice** built on AWS that generates short URLs from original links.

It follows a **stateless, event-driven architecture**, where each request is processed independently by an AWS Lambda function, ensuring high scalability and fault tolerance.

All data is stored in **Amazon S3**, making the solution lightweight, cost-efficient, and easy to maintain.

---

## 🧠 Architecture

```
Client Request (HTTP)
        ↓
API Gateway (Trigger)
        ↓
AWS Lambda (Java)
        ↓
Amazon S3 (JSON Storage)
```

### 🔎 Flow Description

1. Client sends an HTTP request with the original URL  
2. API Gateway triggers the Lambda function  
3. Lambda generates a unique short code (UUID)  
4. URL data is stored as JSON in S3  
5. Shortened URL is returned to the client  

---

## ✨ Features

- 🔗 **URL Shortening:** Unique identifiers using UUID  
- ⚡ **Serverless Execution:** Fully managed with AWS Lambda  
- ☁️ **Cloud Storage:** JSON persistence in Amazon S3  
- ⏱️ **Expiration Control:** Configurable TTL for links  
- 📈 **Highly Scalable:** Auto-scaling with no server management  
- 💰 **Cost Efficient:** Pay-per-use architecture  

---

## 🛠️ Tech Stack

- **Language:** Java 17  
- **Architecture:** Serverless / Event-Driven  
- **Cloud Provider:** AWS  

### ☁️ AWS Services

- **AWS Lambda** → Core business logic  
- **Amazon S3** → Data storage  
- **API Gateway** → HTTP trigger (integration layer)  

---

## 📦 Dependencies

- **AWS SDK for Java v2** → AWS service integration  
- **Jackson Databind** → JSON serialization/deserialization  

---

## 📂 Project Structure

```
src/
└── main/java/com/maruka/createUrlShortener/
    ├── Main.java        # Lambda handler
    └── UrlData.java     # Data model (DTO)

pom.xml                 # Maven dependencies
```

---

## ▶️ Getting Started

### 1. Prerequisites

- AWS Account  
- AWS CLI configured  
- Java 17+  
- Maven  

---

### 2. Build Project

```bash
mvn clean package
```

---

### 3. Deploy to AWS

1. Create an S3 bucket  
   Example: `maruka-urlshortener-storage`

2. Create a Lambda function:
   - Runtime: **Java 17**
   - Upload: `.jar` from `/target`

3. Configure handler:

```
com.maruka.createUrlShortener.Main::handleRequest
```

4. (Optional) Connect API Gateway for HTTP access  

---

## 📄 Example Request

```json
{
  "body": "{\"originalUrl\":\"https://www.google.com\", \"expirationTime\":\"1735689600\"}"
}
```

---

## 🎯 Key Concepts Applied

- Serverless Architecture  
- Stateless Design  
- Event-Driven Systems  
- Cloud-Native Development  
- Scalable Microservices  
- Cost Optimization (Pay-per-use)  

---

## 🤝 Author

**Emanuelle Gomes**  

Software Developer focused on **Cloud, Backend, and Scalable Systems**  
Building modern, efficient, and production-ready applications ☁️🚀
