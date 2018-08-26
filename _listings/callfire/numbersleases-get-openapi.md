---
swagger: "2.0"
x-collection-name: CallFire
x-complete: 0
info:
  title: Callfire Find leases
  description: Searches for all numbers leased by account user. This API is useful
    for finding all numbers currently owned by the user. Returns a paged list of number
    leases.
  termsOfService: https://www.callfire.com/legal/terms
  contact:
    name: CallFire
    url: https://www.callfire.com
    email: support@callfire.com
  version: 1.0.0
host: www.callfire.com
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /keywords/leases:
    get:
      summary: Find keyword leases
      description: Searches for all keywords owned by user. A keyword lease is the
        ownership information involving a keyword
      operationId: findKeywordLeases
      x-api-path-slug: keywordsleases-get
      parameters:
      - in: query
        name: fields
        description: Limit fields received in response
      - in: query
        name: limit
        description: To set the maximum number of records to return in a paged list
          response
      - in: query
        name: offset
        description: Offset to the start of a given page
      responses:
        200:
          description: OK
      tags:
      - Keywords
      - Leases
  /keywords/leases/{keyword}:
    get:
      summary: Find a specific lease
      description: Searches for all keywords owned by user
      operationId: getKeywordLease
      x-api-path-slug: keywordsleaseskeyword-get
      parameters:
      - in: query
        name: fields
        description: Limit fields received in response
      - in: path
        name: keyword
        description: Keyword text that a lease is desired for
      responses:
        200:
          description: OK
      tags:
      - Keywords
      - Leases
      - Keyword
    put:
      summary: Update a lease
      description: Updates a keyword lease. Turns the autoRenew on/off.
      operationId: updateKeywordLease
      x-api-path-slug: keywordsleaseskeyword-put
      parameters:
      - in: body
        name: body
        description: A keyword lease object
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: keyword
        description: To update a keyword lease
      responses:
        200:
          description: OK
      tags:
      - Keywords
      - Leases
      - Keyword
  /numbers/leases:
    get:
      summary: Find leases
      description: Searches for all numbers leased by account user. This API is useful
        for finding all numbers currently owned by the user. Returns a paged list
        of number leases.
      operationId: findNumberLeases
      x-api-path-slug: numbersleases-get
      parameters:
      - in: query
        name: city
        description: A city name
      - in: query
        name: fields
        description: Limit fields received in response
      - in: query
        name: labelName
        description: A label name
      - in: query
        name: lata
        description: A local access and transport area (LATA)
      - in: query
        name: limit
        description: To set the maximum number of records to return in a paged list
          response
      - in: query
        name: offset
        description: Offset to the start of a given page
      - in: query
        name: prefix
        description: A 4-7 digit prefix
      - in: query
        name: rateCenter
        description: A rate center
      - in: query
        name: state
        description: A two-letter state code
      - in: query
        name: zipcode
        description: A five-digit Zipcode
      responses:
        200:
          description: OK
      tags:
      - Numbers
      - Leases
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