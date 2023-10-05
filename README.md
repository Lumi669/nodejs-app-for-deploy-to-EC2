
# The .github/workflows/cicd-workflow.yml is for CI/CD with github actions

- deploy Nodejs application to AWS EC2 using docker and GitHub Actions
- whenever a change is pushed to github respository, it will be published to AWS EC2 instance
- to run the app to get all users, replace the localhost with the `Public IPv4 address` of the EC2 instance in `localhost:5500/rest/getAllUsers` 

- ref: https://www.youtube.com/watch?v=OeLnEB9FDpw

# Nodejs app with rest and graphql example

An example of GraphQL queries/mutations with Node and Express js.

With GraphQL, clients can specify exactly what data they need, and the server responds with only that data, reducing the amount of data transferred over the network.

Rest API Endpoint for get all users: http://localhost:5500/rest/getAllUsers

GraphQL Endpont: http://localhost:5500/graphql

Query for below scenarios: 

1. Get All Users with query operation

query{
  getAllUsers{
    id
    email
  }
}

2. Get single user details

query{
  findUserById(id:1000){
    id
    firstName
    lastName
    email
  }
}

3. Create User with mutation operation

mutation{
  createUser(firstName:"sachin",lastName:"purohit",email:"sachin@sachin.com",password:"password"){
    id
    firstName
    lastName
    email
  }
}
