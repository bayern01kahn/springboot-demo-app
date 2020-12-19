
# springboot-demo-app
### Spring boot application with CRUD operations in Cassandra.

#### Pre-requisites

 1. Java
 2. Cassandra
 3. Maven
 4. init Cassandra with cqlsh
    4.1 docker exec -it xxx  (进入容器)
    4.2 cqlsh
    4.3 CREATE KEYSPACE IF NOT EXISTS user WITH REPLICATION = {'class': 'SimpleStrategy','replication_factor':1};
    4.4 use user;
    4.5 CREATE TABLE user (id int, name varchar, address varchar, salary int, PRIMARY KEY (id) );
    4.6 INSERT INTO user (id, name, address, salary) VALUES (1,'justin', 'some where', 500000);
    4.7 select * from user; 

#### How to run the application?

    mvn spring-boot:run

Application runs on port 5000 by default and that can be changed to desired port from application.properties in resources.

 **1. Create User**
 

    Route(Method - POST) : localhost:5000/user
**Request Body**

    {
    	"id":1000,
    	"address":"Delhi",
    	"name":"Deepak",
    	"salary":6000
    }

 **2. Get All Users**
 

    Route(Method - GET) : localhost:5000/users
  

 **3. Get User**
 

    Route(Method - GET) : localhost:5000/users/{id}

 **4. Delete User**
 

    Route(Method - GET) localhost:5000/deleteUser/{id}

 **5. Update User**
 

    localhost:5000/user/{id}
**RequestBody**

    {
    	"id":1,
    	"address":"Gurgaon",
    	"name":"Deepak",
    	"salary":60000
    }


 **Note -** You need to have Cassandra running on port 9042 before you start the application.
