# api3-ecosystem-backend
Node server for API3 ecosystem platform

## API documentation

#### Get project list with filters

<details>
 <summary><code>GET</code> <code><b>/</b></code> <code>(get list of projects with filters)</code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | page      |  optional | number   | list page number, default set to `1` of not provided  |
> | category      |  optional | string   | project category  |
> | chain      |  optional | number   | Chain Id of projects  |
> | productType      |  optional | string   | Product type of projects, example: Data Feed, Automation, Node etc  |
> | year      |  optional | string   | Project release year  |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `201`         | `application/json`        | `[ ]`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `405`         | `text/html;charset=utf-8`         | None                                                                |
