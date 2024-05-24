# Simple Symfony Project
This project will allow you to demonstrate your skills and proficiency with PHP and the Symfony framework. You're welcome to make it as simple or as advanced as you would like, but the most important factor is ensuring all of the tasks are completed. We recommend spending less than 90 minutes on it as well.

## Project Description
You will be creating a basic HTTP REST API using Symfony 7 and PHP 8. The API does not need to use any kind of authentication, and will be comprised of four endpoints. To keep this project as simple as possible, we recommend using SQLite3 as a database. The API must use JSON as the format for sending and receiving data. Errors should be handled with JSON as the response as well.

### API Endpoints
Your Symfony application needs to respond to four endpoints:

1. `GET /`
2. `GET /customers`
3. `POST /customers`
4. `GET /customers/{customerId}

#### `GET /`
This endpoint should return the version of the API and the name of the server it is currently running on. You're free to make up any version number or scheme you wish.

```json
{
    "version": "0.0.1",
    "server": "localhost"
}
```

#### `GET /customers`
