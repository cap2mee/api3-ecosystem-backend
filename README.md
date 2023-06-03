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
 <summary><code>GET</code> <code><b>/projects</b></code> <code>(get list of projects with filters)</code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
 > | page      |  optional | number   | page number to paginate list of projects  |
> | categories      |  optional | [string]   | param to filter projects with list of categories, since a project can belong multiple categories  |
> | chains      |  optional | [number]   | filter with chains  |
> | productTypes      |  optional | [string]   | filter with project types , example: Data Feed, Automation, Node etc  |
> | year      |  optional | string   | Project release year  |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`        | `  [ { id:'1', name:'Avegotchi', description:"Ultimate gamified defi experience", logo:"url", categories:["Defi", "Dao"], productType:["Vrf", "Automation"],  live:true, approved: true,  chains: [{id:1, name:"Ethereum", chainId:1}, {id:2, name:"Polygon", chainId:137}], year:"2023", releaseDate:"02-01-2023"} ]`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `401`         | `text/html;charset=utf-8`         | Unauthorized                                                                |
> | `500`         | `text/html;charset=utf-8`         | Server error                                                                |
</details>


#### Get project by id

<details>
 <summary><code>GET</code> <code><b>/projects/{project_id}</b></code> <code>(get project detail by id)</code></summary>

##### Parameters
 
> None


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`        | `  { id:'1', name:'Avegotchi', description:"Ultimate gamified defi experience", about:"Yield Protocol utilizing Delta Neutral Strategy Vaults. Delivering risk-hedged, sustainable investment strategies easily     accessible for anyone, anywhere", logo:"url", categories:["Defi", "Dao"], productType:["Vrf", "Automation"],  live:true, approved: true,  chains: [{id:1, name:"Ethereum", chainId:1}, {id:2, name:"Polygon", chainId:137}], year:"2023", releaseDate:"02-01-2023", socials: [{ name:'Twitter', url:""}, {name:"Telegram", url:""} ], website:"url", doc:"url", dappUrl:""   }`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `401`         | `text/html;charset=utf-8`         | Unauthorized                                                                |
> | `500`         | `text/html;charset=utf-8`         | Server error                                                                |
</details>


#### Submit new project listing

<details>
 <summary><code>POST</code> <code><b>/project</b></code> <code>(Create a project listing review on github)</code></summary>

##### Body
 
> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
 > | name      |  required | string   | project name  |
 > | description      |  required | string   | project short description  |
 > | about      |  required | string   | project summary  |
 > | about      |  required | string   | project summary  |
 > | logo      |  required | string   | project logo url |
 > | bannerImage      |  optional | string   | project banner image url |
 > | categories      |  required | [string]   | project categories |
 > | productTypes      |  required | [string]   | project product types |
 > | live      |  required | boolean   | project status |
 > | socials      |  required | [Object]   | project social links, Object: {name, url}  |
 > | chains      |  required | [Object]   | project chains , Object: {name, chainId}  |
 > | year      |  required | string   | project release year  |
 > | date      |  required | Date   | project release date  |
 > | website      |  required | string   | project website url  |
 > | doc      |  required | string   | project documentation url  |
 > | dappUrl      |  required | string   | project dapp url  url  |



##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `201`         | `application/json`        | `  { id:'1', name:'Avegotchi', description:"Ultimate gamified defi experience", about:"Yield Protocol utilizing Delta Neutral Strategy Vaults. Delivering risk-hedged, sustainable investment strategies easily     accessible for anyone, anywhere", logo:"url", categories:["Defi", "Dao"], productType:["Vrf", "Automation"],  live:true, approved: true,  chains: [{id:1, name:"Ethereum", chainId:1}, {id:2, name:"Polygon", chainId:137}], year:"2023", releaseDate:"02-01-2023", socials: [{ name:'Twitter', url:""}, {name:"Telegram", url:""} ], website:"url", doc:"url", dappUrl:""   }`                                |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `401`         | `text/html;charset=utf-8`         | Unauthorized                                                                |
> | `500`         | `text/html;charset=utf-8`         | Server error                                                                |
</details>

