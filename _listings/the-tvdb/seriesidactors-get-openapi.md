---
swagger: "2.0"
x-collection-name: The TVDB
x-complete: 0
info:
  title: The TVDB Get Series Actors
  description: Returns actors for the given series id
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
  /refresh_token:
    get:
      summary: Get Refresh Token
      description: Refreshes your current, valid JWT token and returns a new token.
        Hit this route so that you do not have to post to `/login` with your API key
        and credentials once you have already been authenticated.
      operationId: refresh_token.get
      x-api-path-slug: refresh-token-get
      responses:
        200:
          description: OK
      tags:
      - Television
      - Refresh
      - Token
  /search/series:
    get:
      summary: Get Search Series
      description: Allows the user to search for a series based on the following parameters.
      operationId: search.series.get
      x-api-path-slug: searchseries-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Search
      - Series
  /search/series/params:
    get:
      summary: Get Search Series Params
      description: Returns an array of parameters to query by in the `/search/series`
        route.
      operationId: search.series.params.get
      x-api-path-slug: searchseriesparams-get
      responses:
        200:
          description: OK
      tags:
      - Television
      - Search
      - Series
      - Params
  /series/{id}:
    get:
      summary: Get Series
      description: Returns a series records that contains all information known about
        a particular series id.
      operationId: series.id.get
      x-api-path-slug: seriesid-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
    head:
      summary: Head Series
      description: Returns header information only about the given series ID.
      operationId: series.id.head
      x-api-path-slug: seriesid-head
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
  /series/{id}/actors:
    get:
      summary: Get Series Actors
      description: Returns actors for the given series id
      operationId: series.id.actors.get
      x-api-path-slug: seriesidactors-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Actors
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