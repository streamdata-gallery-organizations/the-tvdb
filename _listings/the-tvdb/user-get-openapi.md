---
swagger: "2.0"
x-collection-name: The TVDB
x-complete: 0
info:
  title: The TVDB Get User
  description: Returns basic information about the currently authenticated user.
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
  /series/{id}/episodes:
    get:
      summary: Get Series Episodes
      description: All episodes for a given series. Paginated with 100 results per
        page.
      operationId: series.id.episodes.get
      x-api-path-slug: seriesidepisodes-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Episodes
  /series/{id}/episodes/query:
    get:
      summary: Get Series Episodes Query
      description: This route allows the user to query against episodes for the given
        series. The response is a paginated array of episode records that have been
        filtered down to basic information.
      operationId: series.id.episodes.query.get
      x-api-path-slug: seriesidepisodesquery-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Episodes
      - Query
  /series/{id}/episodes/query/params:
    get:
      summary: Get Series Episodes Query Params
      description: Returns the allowed query keys for the `/series/{id}/episodes/query`
        route
      operationId: series.id.episodes.query.params.get
      x-api-path-slug: seriesidepisodesqueryparams-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Episodes
      - Query
      - Params
  /series/{id}/episodes/summary:
    get:
      summary: Get Series Episodes Summary
      description: |-
        Returns a summary of the episodes and seasons available for the series.

        __Note__: Season "0" is for all episodes that are considered to be specials.
      operationId: series.id.episodes.summary.get
      x-api-path-slug: seriesidepisodessummary-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Episodes
      - Summary
  /series/{id}/filter:
    get:
      summary: Get Series Filter
      description: Returns a series records, filtered by the supplied comma-separated
        list of keys. Query keys can be found at the `/series/{id}/filter/params`
        route.
      operationId: series.id.filter.get
      x-api-path-slug: seriesidfilter-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Filter
  /series/{id}/filter/params:
    get:
      summary: Get Series Filter Params
      description: Returns the list of keys available for the `/series/{id}/filter`
        route
      operationId: series.id.filter.params.get
      x-api-path-slug: seriesidfilterparams-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Filter
      - Params
  /series/{id}/images:
    get:
      summary: Get Series Images
      description: Returns a summary of the images for a particular series
      operationId: series.id.images.get
      x-api-path-slug: seriesidimages-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Images
  /series/{id}/images/query:
    get:
      summary: Get Series Images Query
      description: Query images for the given series ID.
      operationId: series.id.images.query.get
      x-api-path-slug: seriesidimagesquery-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Images
      - Query
  /series/{id}/images/query/params:
    get:
      summary: Get Series Images Query Params
      description: Returns the allowed query keys for the `/series/{id}/images/query`
        route. Contains a parameter record for each unique `keyType`, listing values
        that will return results.
      operationId: series.id.images.query.params.get
      x-api-path-slug: seriesidimagesqueryparams-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Series
      - Images
      - Query
      - Params
  /updated/query:
    get:
      summary: Get Updated Query
      description: |-
        Returns an array of series that have changed in a maximum of one week blocks since the provided `fromTime`.


        The user may specify a `toTime` to grab results for less than a week. Any timespan larger than a week will be reduced down to one week automatically.
      operationId: updated.query.get
      x-api-path-slug: updatedquery-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Television
      - Updated
      - Query
  /updated/query/params:
    get:
      summary: Get Updated Query Params
      description: Returns an array of valid query keys for the `/updated/query/params`
        route.
      operationId: updated.query.params.get
      x-api-path-slug: updatedqueryparams-get
      responses:
        200:
          description: OK
      tags:
      - Television
      - Updated
      - Query
      - Params
  /user:
    get:
      summary: Get User
      description: Returns basic information about the currently authenticated user.
      operationId: user.get
      x-api-path-slug: user-get
      responses:
        200:
          description: OK
      tags:
      - Television
      - User
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