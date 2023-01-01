- [Learn GraphQL Fundamentals with Fullstack Tutorial (howtographql.com)](https://www.howtographql.com/basics/0-introduction/)
- More powerful, efficient, and flexible alternative to REST
    - At its core, GraphQL enables __declarative data fetching__ where a client can specify exactly what data it needs from an API. Instead of multiple endpoints that return fixed data structures, a GraphQL server only exposes a single endpoint and responds with precisely the data a client asked for.
- 3 Factors challenging the way APIs are designed
    - 1. Increased mobile usage creates need for efficient data loading
    - 2. Variety of different frontend frameworks and platforms
    - 3. Fast development and expectation for rapid feature development
- Why is GraphQL better?
    - Let's look at a case where:
        - To illustrate the major differences between REST and GraphQL when it comes to fetching data from an API, let’s consider a simple example scenario: In a blogging application, an app needs to display the titles of the posts of a specific user. The same screen also displays the names of the last 3 followers of that user. How would that situation be solved with REST and GraphQL?
        - ### Data Fetching with REST vs GraphQL
            - With a REST API, you would typically gather the data by accessing multiple endpoints. In the example, these could be /users/<id> endpoint to fetch the initial user data. Secondly, there’s likely to be a /users/<id>/posts endpoint that returns all the posts for a user. The third endpoint will then be the /users/<id>/followers that returns a list of followers per user.
            - ![](local-asset://Geaux-Notes/pA4JMu8xzb.png)
            - We have three separate requests here
            - ![](local-asset://Geaux-Notes/G5uigsohwF.png)
            - With GraphQL, only one single query
        - ## No more over and underfetching
            - Overfetching: client downloads more data than needed
            - Underfetching: the n+1 problem. Client will have to make additional fetchs for everything they need.
        - ## GraphQL allows rapid product iterations on frontend
        - Insightful analytics on back end
        - ### Benefits of a Schema & Type System
            - GraphQL uses a strong type system to define the capabilities of an API. All the types that are exposed in an API are written down in a __schema__ using the GraphQL Schema Definition Language (SDL). This schema serves as the contract between the client and the server to define how a client can access the data.
            - Once the schema is defined, the teams working on frontend and backends can do their work without further communication since they both are aware of the definite structure of the data that’s sent over the network.
            - Frontend teams can easily test their applications by mocking the required data structures. Once the server is ready, the switch can be flipped for the client apps to load the data from the actual API.
- 
- 
- 
- 
- # Articles
    - [5 Top Reasons Why and How to Use GraphQL | Prisma](https://www.prisma.io/blog/top-5-reasons-to-use-graphql-b60cfa683511)
    - 