# Products Spring Boot REST API

Products API allows clients to create, retrive, update, and delete products data.

## Base URL

"\*/api/products"

## How to run

command to start the app ./mvnw spring-boot:run

## API Endpoints

| Method | Endpoint           | Description        | Success | Error |
| ------ | ------------------ | ------------------ | ------- | ----- |
| GET    | /api/products      | Get all products   | 200     | —     |
| GET    | /api/products/{id} | Get product by ID  | 200     | 404   |
| POST   | /api/products      | Create new product | 201     | 400   |
| PUT    | /api/products/{id} | Update product     | 200     | 404   |
| DELETE | /api/products/{id} | Delete product     | 204     | 404   |

## Curl Examples

#### Create a product

curl -X POST http://localhost:8080/api/products \
 -H "Content-Type: application/json" \
 -d '{"name":"Laptop","category":"Electronics","price":999.99,"quantity":10}'

#### Get all products

curl http://localhost:8080/api/products

#### Get by ID

curl http://localhost:8080/api/products/1

#### Update

curl -X PUT http://localhost:8080/api/products/1 \
 -H "Content-Type: application/json" \
 -d '{"name":"Laptop Pro","category":"Electronics","price":1299.99,"quantity":5}'

#### Delete

curl -X DELETE http://localhost:8080/api/products/1

## Sample response

#### Create a product

{"name":"Keyboard","category":"Electronics","price":999.99,"quantity":10}

#### Get all products

[
{
"id": 1,
"name": "Laptop",
"category": "Electronics",
"price": 999.99,
"quantity": 10
},
{
"id": 2,
"name": "Mouse",
"category": "Electronics",
"price": 999.99,
"quantity": 10
},
{
"id": 3,
"name": "Keyboard",
"category": "Electronics",
"price": 999.99,
"quantity": 10
}
]

#### Get by ID

{
"id": 1,
"name": "Laptop",
"category": "Electronics",
"price": 999.99,
"quantity": 10
}

#### Update

http://localhost:8080/api/products/1

{"id":1,"name":"Laptop Pro","category":"Electronics","price":1299.99,"quantity":5}

#### Delete

curl -X DELETE http://localhost:8080/api/products/3

[
{
"id": 1,
"name": "Laptop Pro",
"category": "Electronics",
"price": 1299.99,
"quantity": 5
},
{
"id": 2,
"name": "Mouse",
"category": "Electronics",
"price": 999.99,
"quantity": 10
}
]
