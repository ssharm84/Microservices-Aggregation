https://www.pogsdotnet.com/2018/09/api-gateway-response-aggregation-with.html

https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html

dotnet new webapi -o Authentication
dotnet new webapi -o Catalog
dotnet new webapi -o Gateway
dotnet new webapi -o Ledger

We finished through ocelot.json where we added the routes of  Catalog, User(from Authentication) and Transaction from Ledger.

We added key for user and transaction so that we can perform aggregation of both user and transaction in the aggregates section:

"Aggregates": [
      {
        "ReRouteKeys": [
          "user-transactions",
          "user-profile"
        ],
        "UpstreamPathTemplate": "/api/user-transactions/{id}"
      }


