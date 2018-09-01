---
swagger: "2.0"
x-collection-name: The TVDB
x-complete: 0
info:
  title: The TVDB Post Login
  description: Returns a session token to be included in the rest of the requests.
    Note that API key authentication is required for all subsequent requests and user
    auth is required for routes in the `User` section
  version: 2.1.2
host: api-dev.thetvdb.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /episodes/{id}:
    get:
      summary: Get Episodes
      description: Returns the full information for a given episode id. __Deprecation
        Warning:__ The _director_ key will be deprecated in favor of the new _directors_
        key in a future release.
      operationId: episodes.id.get
      x-api-path-slug: episodesid-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Episodes
  /languages:
    get:
      summary: Get Languages
      description: All available languages. These language abbreviations can be used
        in the `Accept-Language` header for routes that return translation records.
      operationId: languages.get
      x-api-path-slug: languages-get
      responses:
        200:
          description: OK
      tags:
      - Television
      - Languages
  /languages/{id}:
    get:
      summary: Get Languages
      description: Information about a particular language, given the language ID.
      operationId: languages.id.get
      x-api-path-slug: languagesid-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Languages
  /login:
    post:
      summary: Post Login
      description: Returns a session token to be included in the rest of the requests.
        Note that API key authentication is required for all subsequent requests and
        user auth is required for routes in the `User` section
      operationId: login.post
      x-api-path-slug: login-post
      parameters:
      - in: body
        name: Authentication string
        description: JSON string containing your authentication details
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Television
      - Login
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---