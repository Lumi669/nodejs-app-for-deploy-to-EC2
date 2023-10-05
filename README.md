
# The .github/workflows/cicd-workflow.yml is for CI/CD with github actions

- deploy Nodejs application to AWS EC2 using docker and GitHub Actions
- whenever a change is pushed to github respository, it will be published to AWS EC2 instance
- to run the app to get all users, replace the localhost with the `Public IPv4 address` of the EC2 instance in `localhost:5500/rest/getAllUsers` 

- ref: https://www.youtube.com/watch?v=OeLnEB9FDpw
- Procedures
-  1. Create above workfile in root 
-  2. Add docker username and password to this repository's `Secretes and Variables / Actions` - 
-  3. Launch an EC2 instance 
-  4. in github , this repository's `Settings/Actions/Runners`, click `New self-hosted runnver`, then copy paste the command into the EC2 cloud shell (which is opened via `EC2 Instance Connect` of connect), note: 1. choose Linux because the EC2 instance free tier is on Linux 2. if the EC2 shell freeze, can duplicate it and run `./run.sh` in dir acions-runner (check by `ls -la` first) 3. step 2 is to make sure that the runner is in Idle status instead of Offline which will make the deploying to EC2 waiting. 



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
