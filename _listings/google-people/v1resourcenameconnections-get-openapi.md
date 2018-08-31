---
swagger: "2.0"
x-collection-name: Google People
x-complete: 0
info:
  title: Google People API Get Connections
  description: |-
    Provides a list of the authenticated user's contacts merged with any
    linked profiles.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: people.googleapis.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v1/people:batchGet:
    get:
      summary: Get People
      description: |-
        Provides information about a list of specific people by specifying a list
        of requested resource names. Use `people/me` to indicate the authenticated
        user.
      operationId: people.people.getBatchGet
      x-api-path-slug: v1peoplebatchget-get
      parameters:
      - in: query
        name: requestMask.includeField
        description: Comma-separated list of fields to be included in the response
      - in: query
        name: resourceNames
        description: The resource name, such as one returned by[`people
      responses:
        200:
          description: OK
      tags:
      - People
  /v1/{resourceName}:
    get:
      summary: Get Person
      description: |-
        Provides information about a person resource for a resource name. Use
        `people/me` to indicate the authenticated user.
      operationId: people.people.get
      x-api-path-slug: v1resourcename-get
      parameters:
      - in: query
        name: requestMask.includeField
        description: Comma-separated list of fields to be included in the response
      - in: path
        name: resourceName
        description: The resource name of the person to provide information about
      responses:
        200:
          description: OK
      tags:
      - People
  /v1/{resourceName}/connections:
    get:
      summary: Get Connections
      description: |-
        Provides a list of the authenticated user's contacts merged with any
        linked profiles.
      operationId: people.people.connections.list
      x-api-path-slug: v1resourcenameconnections-get
      parameters:
      - in: query
        name: pageSize
        description: The number of connections to include in the response
      - in: query
        name: pageToken
        description: The token of the page to be returned
      - in: query
        name: requestMask.includeField
        description: Comma-separated list of fields to be included in the response
      - in: query
        name: requestSyncToken
        description: Whether the response should include a sync token, which can be
          used to getall changes since the last request
      - in: path
        name: resourceName
        description: The resource name to return connections for
      - in: query
        name: sortOrder
        description: The order in which the connections should be sorted
      - in: query
        name: syncToken
        description: A sync token, returned by a previous call to `people
      responses:
        200:
          description: OK
      tags:
      - Connection
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