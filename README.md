## api3-ecosystem-backend
Node server for API3 ecosystem platform

### API documentation


 #### Get ecosystem statistics

<details>
 <summary><code>GET</code> <code><b>/project-stats</b></code> <code>(get current ecosystem stats: total projects, projects in each category, chain and product types)</code></summary>

##### Parameters

>  None      



##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`        | `  [ { totalProjects:1200, categories: [{id:'1', name:"Defi", count:50}, {id:2, name:"Dao", count:100}],chains: [{id:1 name:"Ethereum", chainId:1 count:50}, {id:2, name:"Polygon", chainId:137, count:100}] }, productTypes: [{ id:1, name:"Automaton", count:50}, {id:2, name:"VRF", count:100}],  years: [{ id:1, name:"2019", count:50}, {id:2, name:"2020", count:100}] ]`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `401`         | `text/html;charset=utf-8`         | Unauthorized                                                                |
> | `500`         | `text/html;charset=utf-8`         | Server error                                                                |
 </details>
 
 
#### Get project list with filters

<details>
 <summary><code>GET</code> <code><b>/projects/:page</b></code> <code>(get list of projects with filters)</code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | categories      |  optional | [string]   | param to filter projects with list of categories, since a project can belong multiple categories  |
> | chains      |  optional | [number]   | filter with chains  |
> | productTypes      |  optional | [string]   | filter with project types , example: Data Feed, Automation, Node etc  |
> | year      |  optional | string   | Project release year  |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`        | `  [ { id:'1', name:'Avegotchi', description:"Ultimate gamified defi experience", about:"Yield Protocol utilizing Delta Neutral Strategy Vaults. Delivering risk-hedged, sustainable investment strategies easily     accessible for anyone, anywhere", logo:"url", categories:["Defi", "Dao"], productType:["Vrf", "Automation"],  live:true, approved: true,  chains: [{id:1, name:"Ethereum"}, {id:137, name:"Polygon"}], year:"2023", releaseDate:"02-01-2023", socials: [{ name:'Twitter', url:""}, {name:"Telegram", url:""} ], website:"url", doc:"url", appLink:""   } ]`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `401`         | `text/html;charset=utf-8`         | Unauthorized                                                                |
> | `500`         | `text/html;charset=utf-8`         | Server error                                                                |
</details>
