GraphQL in Spring Boot example
==============================

## GraphQL Schema

http://localhost:8080/graphql/schema.json

![](Screenshots/graphql_schema.json.png)

## GraphiQL

http://localhost:8080/graphiql

![](Screenshots/graphiql.png)

## Usage demo

### GET

#### GraphiQL demo

![](Screenshots/graphql.gif)

#### Postman demo

GET request

`
http://localhost:8080/graphql?query={findAllBooks{title pageCount isbn author{firstName lastName}}}
`

Note the query string:
`{findAllBooks{title pageCount isbn author{firstName lastName}}}`

> Postman URL encodes the request for us, which is what our application requires too.

![](Screenshots/postman_get.png)

> If you are testing in the browser you  need a full URL encoded string or you will get a 400 response from the server:

> `http://localhost:8080/graphql?query=%7BfindAllBooks%7Btitle%20pageCount%20isbn%20author%7BfirstName%20lastName%7D%7D%7D`

---

### POST

> The endpoint url is still http://localhost:8080/graphql.

#### GraphiQL

Query syntax：

```
{
  findAllBooks {
    title
    pageCount
    isbn
    author {
      firstName
      lastName
    }
  }
}
```

#### Postman

> Postman will need valid JSON in the request body.

```
{
    "query": "{findAllBooks {title pageCount isbn author {firstName lastName}}}"
}
```

![](Screenshots/postman_post.png)

![](Screenshots/graphql-postman.gif)

## Reference materials

- https://www.pluralsight.com/guides/building-a-graphql-server-with-spring-boot
- https://blog.pusher.com/writing-graphql-service-using-kotlin-spring-boot
