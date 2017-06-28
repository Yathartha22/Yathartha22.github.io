---
layout: post
title: API and Django Rest Framework
comments: true
tags: [ Django, web framework, Python, API ]
---

I have been learning Django, and meanwhile, I came across API and thought how to build them. Consequently, I found **Django Rest Framework**, commonly known as DRF. Before going deep into the topic let's get clear with the definition what actually an API is.

API as defined by [Wikipedia](https://en.wikipedia.org/wiki/Application_programming_interface),

> _In computer programming, an Application Programming Interface (API) is a set of subroutine definitions, protocols, and tools for building application software. In general terms, it is a set of clearly defined methods of communication between various software components._

Bit technical, let me make it more simple for you. Think of an API as a waiter in a restaurant. You are sitting on a table with a menu of choices to order from and a kitchen is a part of the system that will prepare your order, what's missing is the critical link to communicate your order to the kitchen and deliver food back to you. This is where a waiter or an API comes into action.

**API** is an interface between the _Application_ and the _Program_. You might have heard of Youtube API, what does it mean is Youtube API will be a set of functions or procedure that you can use to run youtube functionality on your website(or any application). A good API makes it easier to develop a program by providing all the building blocks. A programmer then puts the blocks together.

I guess API term might have cleared by now. So let's get started with what actually is DRF.

**DRF**

![](/public/DRF.png)

As defined in the official [documentation of DRS](http://www.django-rest-framework.org/)

> Django REST framework is a powerful and flexible toolkit for building Web APIs.

The term REST stands for **Representational State Transfer (REST).**  REST advocates that web applications should use HTTP as it was originally envisioned. Lookups should use GETrequests. PUT, POST, and DELETE requests should be used for creation, mutation, and deletion. I am not going into much detail about what REST is. You can refer to [this](https://stackoverflow.com/a/671132/6446166) Stackoverflow answer for details.


Django REST framework contains a wide set of out of the box features, but the core view class is very simple and framework, in general, is easy to use.


The main idea behind of DRF is to clearly divide a model, the generalized wire representation (e.g. JSON, XML, etc.), and set of generic Class-Based-Views that can be customized to satisfy the specific API endpoint using Serializer that describes the mapping between them.


What I like about DRF, which makes it different from other framework is that it allows developers to define URL structure and not rely on an auto-generated one, while others automate much of the conversion from Django models to REST endpoints, thus are less flexible.


Moreover, Django REST Framework includes built-in API browser for testing out newly developed API.


DRF provides a set of authentication policies out of the box (including [OAuth1a](http://www.django-rest-framework.org/api-guide/authentication#oauthauthentication) and [OAuth2](http://www.django-rest-framework.org/api-guide/authentication#oauth2authentication) and gives an opportunity to develop custom schemes.


Still, I have to learn a lot of stuff in DRF I will keep posting whatever new and interesting things I learn  
