---
title: "Over-fetching vs Under-fetching"
datePublished: Fri Apr 07 2023 16:42:58 GMT+0000 (Coordinated Universal Time)
cuid: clg6rzref000s09mlffjdhrgd
slug: over-fetching-vs-under-fetching
tags: over-fetching-vs-under-fetching

---

Over-fetching and under-fetching are two common issues that can occur when designing APIs, particularly in RESTful API design.

Over-fetching occurs when an API returns more data than is actually needed for a particular request. This can lead to increased network traffic, longer response times, and unnecessary resource consumption. For example, if an API endpoint returns all of a user's profile information when only their username is needed, this would be considered over-fetching.

Under-fetching, on the other hand, occurs when an API endpoint does not provide enough data to satisfy a request, leading to the need for additional requests. This can lead to slower response times, increased network traffic, and more complex code on the client side. For example, if an API endpoint only returns a list of user IDs, but not their corresponding usernames, additional requests may be needed to obtain the necessary information, resulting in under-fetching.

Both over-fetching and under-fetching can have a negative impact on the performance and usability of an API, so it's important to design APIs that minimize these issues. One way to address over-fetching is to provide more granular API endpoints that return only the data that is needed for a particular request. This can help to reduce the amount of data that is returned and improve response times. To address under-fetching, APIs can provide additional data or related resources in the response to a request, allowing clients to obtain all of the necessary data in a single request. Alternatively, APIs can support more complex queries or batch operations that allow clients to retrieve multiple resources in a single request, reducing the need for multiple requests.