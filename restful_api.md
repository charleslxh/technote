# References

- https://martinfowler.com/articles/richardsonMaturityModel.html
- [Web API Design - Crafting Interfaces that Developers Love](http://apigee.com/about/resources/webcasts/restful-api-design-second-edition), you need to input your email to receive the ebook. **[MUST READ]** :bangbang:
- http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api
- http://github.com/interagent/http-api-design

# Examples

- http://developer.github.com/v3

# URL Design Rules

- Remember, REST is **resource oriented**
- Use plural noun for resource collection, like `/blogs`
- To operate on single resource, use URL like `/blogs/1234`
- Use HTTP verbs right
- Common CRUD cases:

    Resource | POST | GET | PUT | PATCH | DELETE
    -------- | ---- | --- | --- | ----- | ------
    /blogs | create a new dog | list blogs | bulk update blogs | X | delete all blogs
    /blogs/1234 | X | show a dog | update a dog | update a dog partially | delete a dog

- For non-resource-CRUD cases, always use POST verb, eg. `POST /machines/1234/restart`

# Misc

## HTTP Verbs

Verb | Safe? | Idempotent? | Scenario |
-----| ---- | ---------- | -------- |
OPTIONS | Y | Y | get communication options(at least available verbs) |
GET | Y | Y | get resource |
HEAD | Y | Y | same with GET but no response body |
PUT | N | Y | create(if not exists)/relpace resource |
DELETE | N | Y | delete resource |
POST | N | N | create resource, unsafe operations there are no suitable verbs for |
PATCH | N | N | update resource partially |

## RESTful api vs RPC style web service

RPC(SOAP):

- Use HTTP for tranfering enveloped data, only use POST verb.
- The key is method.
- Heavyweight.

RESTful:

- Stanard HTTP verbs for CRUD(POST, GET, PUT/PATCH, DELETE).
- The key is resource, resource-oriented.
- Lightweight, cross platform easily.

REST-RPC:

- No envelop, but also no standard HTTP verbs, represent method info in URI.
