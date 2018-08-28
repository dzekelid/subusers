swagger: "2.0"
x-collection-name: 123FormBuilder
x-complete: 1
info:
  title: ""
  version: 1.0.0
host: api.123contactform.com
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /users:
    get:
      summary: Get info about master user and subusers
      description: Get info about master user and subusers
      operationId: get-info-about-master-user-and-subusers
      x-api-path-slug: users-get
      parameters:
      - in: query
        name: JWT
        description: JWT authentication token
      - in: query
        name: page
        description: Page number
      - in: query
        name: per_page
        description: The number of groups to get per page in a request
      responses:
        200:
          description: OK
      tags:
      - Info
      - About
      - Master
      - User
      - Subusers
    post:
      summary: Create a new subuser
      description: Create a new subuser
      operationId: create-a-new-subuser
      x-api-path-slug: users-post
      parameters:
      - in: formData
        name: admin
        description: Indicates if the subuser is admin or not
      - in: formData
        name: allow_create_form
        description: Allow or restrict subuser access to creating new forms
      - in: formData
        name: allow_delete_form
        description: Allow subusers to delete forms
      - in: formData
        name: allow_duplicate_form
        description: Allow subusers to duplicate forms
      - in: formData
        name: can_manage_groups
        description: Allow admin subusers to manage groups
      - in: formData
        name: can_manage_users
        description: Allow admin subusers to manage users
      - in: formData
        name: company_name
        description: The name of the company to which the subuser belongs
      - in: formData
        name: email
        description: Email address of the account
      - in: formData
        name: JWT
        description: JWT authentication token
      - in: formData
        name: name
        description: Username of the account
      - in: formData
        name: passhash
        description: MD5 password
      - in: formData
        name: password
        description: Plain text password
      responses:
        200:
          description: OK
      tags:
      - New
      - Subuser