# Insomnia: Calling APIs

## Terminology: REST API

### API

a set of functions and procedures allowing the creation of applications that
access the features or data of an operating system, application, or other
service. An application programming interface defines the
kinds of calls or requests that can be made, how to make them, the data formats
that should be used, the conventions to follow.

### REST

Representational state transfer (REST) is a software architectural style that
defines a set of constraints to be used for creating Web services. RESTful Web
services allow the requesting systems to access and manipulate textual
representations of Web resources by using a uniform and predefined set of
stateless operations (CRUD).

## HTTP

### Resources

- [HTTP Status Codes](https://http.cat/)

- [HTTP Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

### Requests

|          | Example                                                      |
| -------- | ------------------------------------------------------------ |
| Method   | `GET POST PUT PATCH DELETE OPTION HEAD`                      |
| Base URL | `https://api.chucknorris.io/`                                |
| Path     | `/jokes/random`                                              |
| Query    | `?\_limit=20&\_page=3`                                       |
| Headers  | `"Content-type": "application/json;"`                        |
| Body     | JSON, e.g. `{"name": "Rick", "password": "secret-password"}` |

### Responses

|             | Example                           |
| ----------- | --------------------------------- |
| Status Code | 200 404 400 300, etc...           |
| Headers     | `"Cache-Control": "max-age=3600"` |
| Body        | json, html, js, css, png, ...     |

### Insomnia

Insomnia is a GUI tool to execute HTTP Requests. You can use it to
call any Web Service API. Start by installing it on your
computer:

[insomnia.rest](https://insomnia.rest/)

### API Challenge

Use Insomnia and the linked API's and their documentation to complete these
tasks. Don't Google the answers!!!

- Find a Chuck Norris Joke about linux.
- Alofi is the capital of which country.
- Get some programming quote
- Download the astronomy picture of the day
- How many github repositories are written in javascript compared to python or php
- Get the version of google.com from the 1. January 2000
- Generate a random Avatar
- For how many deaths was Walter White responsible throughout the series
  Breaking Bad
- Get a wheather forecast for Leipzig
- Use the Github API to render some markdown to html
- Get the Github gitignore template for a node application

#### API's

- [Chuck Norris API](https://api.chucknorris.io/)
- [Country API](https://restcountries.eu/)
- [Programming Quotes API](https://programming-quotes-api.herokuapp.com/)
- [NASA API](https://api.nasa.gov/index.html)
- [GitHub API](https://docs.github.com/en/rest/reference)
- [Internet Archive API](https://archive.readme.io/docs/website-snapshots)
- [Avatar Generator API](https://avatars.dicebear.com/)
- [Breaking Bad API](https://breakingbadapi.com/documentation)
- [Meta Wheather API](https://www.metaweather.com/api/)

## CRUD

**C**reate **R**ead **U**pdate **D**elete

### Resources

- [API Best practices](https://github.com/elsewhencode/project-guidelines#api)
- [JSON Server Reference](https://github.com/typicode/json-server)

### REST CRUD Routes for a resource

| Operation        | Method | Route    | Body                             | Response                 |
| ---------------- | ------ | -------- | -------------------------------- | ------------------------ |
| Create           | POST   | /posts   | New post                         | The created post         |
| Find All         | GET    | /posts   |                                  | Array of posts           |
| Find One         | GET    | /posts/1 |                                  | Post with the id 1       |
| Update (replace) | PUT    | /posts/1 | Complete updated version of post | The updated post         |
| Update (patch)   | PATCH  | /posts/1 | Partial updated version of post  | The complete update post |
| Delete           | DELETE | /posts/1 |                                  | Delete post              |

### Query Parameters

Get all users named Bret

```none
GET /users?name=Bret
```

Get 3 page of posts, with 10 posts per page

```none
GET /posts?_limit=10&_page=3
```

Get all posts sorted by title

```none
GET /posts?_sort=title&_order=asc
```

For the full list of query parameters supported by the _json-placeholder_ api,
see <https://github.com/typicode/json-server>

### CRUD REST API Exercise

Clone and run this fake json server: <https://github.com/gabrielheinrich/fake-rest-server>

Create the following requests in Insomnia.
A documentation of all the features of the api can be found at
<https://github.com/typicode/json-server>

1. Get all users
2. Get the photos for page 2 with 8 photos per page
3. Get the post with the id 42
4. What status code and body is the API returning if you get the todo with the
   id 999
5. Create a new todo
6. Delete the todo with id 4
7. Update the todo with the id 6
8. Update only the completed status of the todo with the id 6
9. Do a full text search on the posts for the search term **dolor**
10. Every post has a userId. Get all posts, but with each user expanded with the
    data from the /users resource. Check the documentation first for how to do this.

Extra: Look at the structure of the data.json file in the repository. Replace
the contents of the file to resemble the database of an online store with
products, customers and orders and create API requests for common operations.

Extra Extra: In the same manner design a database layout for another application
of your choosing.

## Explore

Browse through these public api's, pick one and try to call it with insomnia.

https://github.com/public-apis/public-apis
