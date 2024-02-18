# API's

- tags: #API
---

# Tools
* [Paw ](https://paw.cloud)- API tool for Mac (like Postman)
* [Dash](https://kapeli.com/dash) - API Documentation Browser and Code Snippet Manager for Mac (alt for [Zeal](https://zealdocs.org))
* [HTTPie](https://github.com/httpie/httpie) - human-friendly CLI HTTP client

### Fake API for testing and prototyping

* [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)
* [https://httpbin.org/json](https://httpbin.org/json)

---

# Info

## Documenting APIs: A guide for technical writers and engineers

* [https://idratherbewriting.com/learnapidoc/](https://idratherbewriting.com/learnapidoc/)

## API Security Checklist

* [https://github.com/shieldfy/API-Security-Checklist](https://github.com/shieldfy/API-Security-Checklist)&#x20;

## JSON API in excel

* [https://www.howtoexcel.org/power-query/how-to-access-a-json-api-with-power-query/](https://www.howtoexcel.org/power-query/how-to-access-a-json-api-with-power-query/)
* [https://syntaxbytetutorials.com/import-json-data-in-excel-2016-or-2019-or-office-365-using-a-get-transform-query/](https://syntaxbytetutorials.com/import-json-data-in-excel-2016-or-2019-or-office-365-using-a-get-transform-query/)
* [https://syntaxbytetutorials.com/excel-import-coinmarketcap-api-data-with-query/](https://syntaxbytetutorials.com/excel-import-coinmarketcap-api-data-with-query/)

## REST, SOAP OR GRAPHQL?

When you make a data query in GraphQL, you specify exactly what you wish to receive. Such results are achieved through shifting the data definition functions to the client side, while in REST, data is defined on the server side. In other words, in REST API architecture, the server defines which data is to be returned, while in GraphQL API, the server only declares the available data, and the client specifies what should be returned.

Another thing you should consider while choosing the API protocol is data caching. Caching eliminates the need to send full requests and responses in case data has been cached from previous requests. REST API uses the HTTP caching mechanism that provides quite satisfactory results. At the same time, GraphQL has no inherent caching and requires additional mechanisms on the client side, such as **Apollo Client**.

* **SOAP** can be used in enterprise solutions with formal contract-based exchange formats. Also, SOAP APIs perform best when there are acceleration mechanisms implemented on both sides.
* **REST** is very JavaScript-friendly, so it is a perfect choice for JavaScript-based applications. Besides, it can cope with higher loads and process data quicker than SOAP. Thus if your application is rather load-intensive, REST may be your API of choice.
* **GraphQL** can show the best performance when the number of queries needs to be reduced to the absolute minimum. With its single query addressing multiple resources, GraphQL can be a good match to this challenge. Also, considering the fact that in GraphQL data is defined on the client side, it can be a good solution for cases when there is no dependency between the client application and the server.
* [https://da-14.com/blog/ultimate-guide-api-architecture-rest-soap-or-graphql](https://da-14.com/blog/ultimate-guide-api-architecture-rest-soap-or-graphql)