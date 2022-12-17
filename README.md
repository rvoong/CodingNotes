**Structure of the program**
<img src="structure.jpeg" alt="">

1.  When the submit button is clicked, an HTTP request is sent to the RESTFUL api

2.  RESTful(Representational State Transfer) API simplified

- A web API that obeys the REST constraints is informally described as RESTful.
- In a RESTful Web service, requests made to a resource's URI (Uniform resource identifier) elicit a response with a payload formatted in HTML, XML, JSON, or some other format. The most common protocol for these requests and responses is HTTP, which provides operations (HTTP methods) such as OPTIONS, GET, POST, PUT, PATCH and DELETE.
- Uses transfer protocol to run CRUD operations (Create, read, update, delete)

| CRUD   | HTTP                                |
| ------ | ----------------------------------- |
| Create | POST, PUT if we have `id` or `uuid` |
| Read   | GET                                 |
| Update | PUT                                 |
| Delete | DELETE                              |
