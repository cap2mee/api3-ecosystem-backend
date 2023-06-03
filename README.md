## api3-ecosystem-backend
Node server for API3 ecosystem platform

### API documentation

#### Get project list with filters

<details>
 <summary><code>GET</code> <code><b>/projects/:page</b></code> <code>(get list of projects with filters)</code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | categories      |  optional | string   | project category  |
> | chain      |  optional | number   | Chain Id of projects  |
> | productType      |  optional | string   | Product type of projects, example: Data Feed, Automation, Node etc  |
> | year      |  optional | string   | Project release year  |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`        | `  [ { id:'1', name:'Avegotchi', description:"Ultimate gamified defi experience", about:"Yield Protocol utilizing Delta Neutral Strategy Vaults. Delivering risk-hedged, sustainable investment strategies easily     accessible for anyone, anywhere", logo:"url", categories:["Defi", "Dao"], productType:["Vrf", "Automation"],  live:true, approved: true,  chains: [{id:1, name:"Ethereum"}, {id:137, name:"Polygon"}], year:"2023", releaseDate:"02-01-2023", socials: [{ name:'Twitter', url:""}, {name:"Telegram", url:""} ], website:"url", doc:"url", appLink:""   } ]`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `401`         | `text/html;charset=utf-8`         | Unauthorized                                                                |
> | `500`         | `text/html;charset=utf-8`         | Server error                                                                |
