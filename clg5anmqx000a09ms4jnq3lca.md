---
title: "how to write a blog article to hash node through code"
datePublished: Thu Apr 06 2023 15:49:53 GMT+0000 (Coordinated Universal Time)
cuid: clg5anmqx000a09ms4jnq3lca
slug: how-to-write-a-blog-article-to-hash-node-through-code
tags: blogging

---

To write a blog article to Hashnode through Python code, you can use the `requests` library to make HTTP requests to the Hashnode API. Here are the steps to create a new article:

1. Obtain an API key from Hashnode. You can do this by creating a Hashnode account, navigating to the API settings page, and generating a new API key.
    
2. Install the `requests` library using pip. Open a terminal or command prompt and run:
    
    ```python
    pip install requests
    ```
    
3. Create a Python script and import the `requests` library. Define the required parameters for the article, such as the title, content, and tags.
    
    ```python
    import requests
    
    API_ENDPOINT = 'https://api.hashnode.com'
    API_KEY = 'YOUR_API_KEY_HERE'
    
    title = 'My first Hashnode article'
    content = 'Hello, world!'
    tags = ['hashnode', 'api']
    ```
    
4. Define a function that sends a POST request to the Hashnode API to create a new article. Use the [`requests.post`](http://requests.post)`()` method to send the request, and pass the API key and the article parameters in the request body.
    
    ```python
    def create_article(title, content, tags):
        url = f'{API_ENDPOINT}/v1/posts'
        headers = {
            'Authorization': f'Bearer {API_KEY}',
            'Content-Type': 'application/json',
        }
        data = {
            'title': title,
            'content': content,
            'tags': tags,
            'publicationStatus': 'PUBLISHED',
            'isRepublished': False,
        }
        response = requests.post(url, headers=headers, json=data)
        response.raise_for_status()
        return response.json()['data']
    ```
    
    In this example, the `create_article()` function sends a POST request to the `/v1/posts` endpoint of the Hashnode API, with the required parameters in the request body, and the API key in the `Authorization` header. The function returns the JSON response of the API, which includes the ID of the newly created article.
    
5. Call the `create_article()` function with the article parameters, and print the response to verify that the article is successfully created on Hashnode.
    
    ```python
    article = create_article(title, content, tags)
    print(f'Created article {article["title"]} with ID {article["_id"]}')
    ```
    
6. Save the Python script and run it from the terminal or command prompt.
    
    ```python
    python create_article.py
    ```
    
    This will send a POST request to the Hashnode API with the specified article parameters, create a new article on your Hashnode blog, and print the response to the console.
    

By following these steps, you can create a new article on Hashnode using Python code and automate the process of publishing content to your blog.