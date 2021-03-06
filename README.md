EpiPic
======

EpiPic is a simple Photo collection app, It will be composed of two distinct parts: The API is responsible for providing
endpoints to manage (browse, add, delete) photos. The front end is responsible for displaying it.


Pre-requisites
--------------

- NodeJS 7.9.0
- Yarn 0.24.6
- Express 4.15.2

API Requests
-----------------

`GET on /api/pictures`

This is the route that will fetch your pictures informations,
This route is paginated by using query params, example : 
`/api/pictures?cursor=99&amount=50` will return the pictures with indexes from 100 to 149.
A request with a cursor out of bounds will return a status 404. The first request obviously has an amount but no
cursor. Base it on the index field instead of id .

`POST on /api/pictures`

This is the route that will insert a new picture in the image collection. The data is expected to come as part of the
request body as a stringified JSON. If the received object does not contain a valid picture field, the endpoint 
will fail and return a status 500.

`DELETE on /api/pictures/:id`

Will delete the picture with the matching id.

Screenshots
-----------

<img src="https://imgur.com/hrH9fZ6.png" width="250">
