---
swagger: "2.0"
x-collection-name: SendGrid
x-complete: 0
info:
  title: SendGrid Get Subusers Stats Sums
  description: |-
    **This endpoint allows you to retrieve the total sums of each email statistic metric for all subusers over the given date range.**


    While you can always view the statistics for all email activity on your account, subuser statistics enable you to view specific segments of your stats. Emails sent, bounces, and spam reports are always tracked for subusers. Unsubscribes, clicks, and opens are tracked if you have enabled the required settings.

    For more information, see our [User Guide](https://sendgrid.com/docs/User_Guide/Statistics/subuser.html).
  version: 1.0.0
host: api.sendgrid.com
basePath: /v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /subusers:
    get:
      summary: Get Subusers
      description: |-
        This endpoint allows you to retrieve a list of all of your subusers. You can choose to retrieve specific subusers as well as limit the results that come back from the API.

        For more information about Subusers:

        * [User Guide > Subusers](https://sendgrid.com/docs/User_Guide/Settings/Subusers/index.html)
        * [Classroom > How do I add more subusers to my account?](https://sendgrid.com/docs/Classroom/Basics/Account/how_do_i_add_more_subusers_to_my_account.html)
      operationId: GET_subusers
      x-api-path-slug: subusers-get
      parameters:
      - in: query
        name: limit
        description: The number of results you would like to get in each request
      - in: query
        name: offset
        description: The number of subusers to skip
      - in: query
        name: username
        description: The username of this subuser
      responses:
        200:
          description: OK
      tags:
      - Email
      - Subusers
    post:
      summary: Add Subusers
      description: |-
        This endpoint allows you to retrieve a list of all of your subusers. You can choose to retrieve specific subusers as well as limit the results that come back from the API.

        For more information about Subusers:

        * [User Guide > Subusers](https://sendgrid.com/docs/User_Guide/Settings/Subusers/index.html)
        * [Classroom > How do I add more subusers to my account?](https://sendgrid.com/docs/Classroom/Basics/Account/how_do_i_add_more_subusers_to_my_account.html)
      operationId: POST_subusers
      x-api-path-slug: subusers-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Email
      - Subusers
  /subusers/reputations:
    get:
      summary: Get Subusers Reputations
      description: |-
        Subuser sender reputations give a good idea how well a sender is doing with regards to how recipients and recipient servers react to the mail that is being received. When a bounce, spam report, or other negative action happens on a sent email, it will effect your sender rating.

        This endpoint allows you to request the reputations for your subusers.
      operationId: subusers.reputations.get
      x-api-path-slug: subusersreputations-get
      parameters:
      - in: query
        name: usernames
      responses:
        200:
          description: OK
      tags:
      - Email
      - Subusers
      - Reputations
  /subusers/stats:
    get:
      summary: Get Subusers Stats
      description: |-
        **This endpoint allows you to retrieve the email statistics for the given subusers.**

        You may retrieve statistics for up to 10 different subusers by including an additional _subusers_ parameter for each additional subuser.

        While you can always view the statistics for all email activity on your account, subuser statistics enable you to view specific segments of your stats. Emails sent, bounces, and spam reports are always tracked for subusers. Unsubscribes, clicks, and opens are tracked if you have enabled the required settings.

        For more information, see our [User Guide](https://sendgrid.com/docs/User_Guide/Statistics/subuser.html).
      operationId: subusers.stats.get
      x-api-path-slug: subusersstats-get
      parameters:
      - in: query
        name: aggregated_by
        description: How to group the statistics
      - in: query
        name: end_date
        description: The end date of the statistics to retrieve
      - in: query
        name: limit
        description: Limits the number of results returned per page
      - in: query
        name: offset
        description: The point in the list to begin retrieving results from
      - in: query
        name: start_date
        description: The starting date of the statistics to retrieve
      - in: query
        name: subusers
        description: The subuser you want to retrieve statistics for
      responses:
        200:
          description: OK
      tags:
      - Email
      - Subusers
      - Stats
  /subusers/stats/monthly:
    get:
      summary: Get Subusers Stats Monthly
      description: |-
        **This endpoint allows you to retrieve the monthly email statistics for all subusers over the given date range.**

        While you can always view the statistics for all email activity on your account, subuser statistics enable you to view specific segments of your stats for your subusers. Emails sent, bounces, and spam reports are always tracked for subusers. Unsubscribes, clicks, and opens are tracked if you have enabled the required settings.

        When using the `sort_by_metric` to sort your stats by a specific metric, you can not sort by the following metrics:
        `bounce_drops`, `deferred`, `invalid_emails`, `processed`, `spam_report_drops`, `spam_reports`, or `unsubscribe_drops`.

        For more information, see our [User Guide](https://sendgrid.com/docs/User_Guide/Statistics/subuser.html).
      operationId: subusers.stats.monthly.get
      x-api-path-slug: subusersstatsmonthly-get
      parameters:
      - in: query
        name: date
        description: The date of the month to retrieve statistics for
      - in: query
        name: limit
        description: Optional field to limit the number of results returned
      - in: query
        name: offset
        description: Optional beginning point in the list to retrieve from
      - in: query
        name: sort_by_direction
        description: The direction you want to sort
      - in: query
        name: sort_by_metric
        description: The metric that you want to sort by
      - in: query
        name: subuser
        description: A substring search of your subusers
      responses:
        200:
          description: OK
      tags:
      - Email
      - Subusers
      - Stats
      - Monthly
  /subusers/stats/sums:
    get:
      summary: Get Subusers Stats Sums
      description: |-
        **This endpoint allows you to retrieve the total sums of each email statistic metric for all subusers over the given date range.**


        While you can always view the statistics for all email activity on your account, subuser statistics enable you to view specific segments of your stats. Emails sent, bounces, and spam reports are always tracked for subusers. Unsubscribes, clicks, and opens are tracked if you have enabled the required settings.

        For more information, see our [User Guide](https://sendgrid.com/docs/User_Guide/Statistics/subuser.html).
      operationId: subusers.stats.sums.get
      x-api-path-slug: subusersstatssums-get
      parameters:
      - in: query
        name: aggregated_by
        description: How to group the statistics
      - in: query
        name: end_date
        description: The end date of the statistics to retrieve
      - in: query
        name: limit
        description: Limits the number of results returned per page
      - in: query
        name: offset
        description: The point in the list to begin retrieving results from
      - in: query
        name: sort_by_direction
        description: The direction you want to sort
      - in: query
        name: sort_by_metric
        description: The metric that you want to sort by
      - in: query
        name: start_date
        description: The starting date of the statistics to retrieve
      responses:
        200:
          description: OK
      tags:
      - Email
      - Subusers
      - Stats
      - Sums
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