# Authentication and Authorization Overview

## Table of Contents
1. [What is Authentication?](#1-what-is-authentication)
2. [What is JWT?](#2-what-is-jwt)
3. [What is Session-based Authentication?](#3-what-is-session-based-authentication)
4. [What is OAuth?](#4-what-is-oauth)
5. [What is Authorization?](#5-what-is-authorization)
6. [Access Token vs Refresh Token](#6-access-token-vs-refresh-token)

---

## 1. What is Authentication?
Authentication is the process of verifying the identity of a user, usually using credentials or tokens.

Common authentication methods are:
- Token-based authentication (JWT)
- Session-based authentication
- OAuth

---

## 2. What is JWT?
JWT (JSON Web Token) is a token-based authentication method that uses to  securely send user information  between client and server in token form.

- A JWT token has three parts: **Header**, **Payload**, and **Signature**
  - **Header** → Contains token type and signing algorithm
  - **Payload** → Contains user data
  - **Signature** → Used to verify token integrity, created using header + payload + secret key

- How it works:
  - When a user logs in,
  - The server generates a token and sends it to the client.
  - The client stores it in LocalStorage, SessionStorage, or Cookies and sends it with every request for authentication.

---

## 3. What is Session-based Authentication?
- Session-based authentication is a method where the server creates and stores session data on server side and sends a session ID to the client.
- which client send with each request
- and the server verifies it using stored session data.
-  When the user logs out or the session expires, the session data get destroyed.

It is **stateful** as server stores session information.

---

## 4. What is OAuth?
- OAuth is an authorization framework that allows users to log in using third-party services like Google, GitHub, etc.,
- without sharing their passwords with the application.

How it works:
- When you click on a third-party service,
- It verifies your identity,
- Then provides a secure token to application,
- Application Use this token to access the limited user data.

---

## 4. What is Authorization?
Authorization is the process that determines what actions or resources an authenticated user is permitted to access.

---

## 6. Access Token vs Refresh Token

| **Access Token**                | **Refresh Token**                      |
|---------------------------------|----------------------------------------|
| Used to access APIs             | Used to get a new access token       |
| Short-lived (minutes)           | Long-lived (days/weeks)               |
| Sent with every request         | Not sent with every request           |

---
