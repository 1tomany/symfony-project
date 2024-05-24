# Simple Symfony Project
This project will allow you to demonstrate your skills and proficiency with PHP and the Symfony framework. You're welcome to make it as simple or as advanced as you would like, but the most important factor is ensuring all of the tasks are completed. We recommend spending less than 90 minutes on it as well.

## Project Description
You will be creating a basic HTTP REST API using Symfony 7 and PHP 8. The API does not need to use any kind of authentication, and will be comprised of four endpoints. To keep this project as simple as possible, we recommend using SQLite3 as a database. The API will use JSON as the format for sending and receiving data. Errors should be handled with JSON as the response as well.

### API Endpoints
Your Symfony application needs to respond to four endpoints:

1. `GET /`
2. `GET /customers`
3. `POST /customers`
4. `GET /customers/{customerId}`

#### `GET /`
This endpoint will return the version of the API and the name of the server it is currently running on. You're free to make up any version number or scheme you wish.

```json
{
    "version": "0.0.1",
    "server": "localhost"
}
```

#### `GET /customers`
This endpoint will return all customers in the database sorted by the date they were created in ascending order. A customer should have the following properties:

- `id`
- `createdAt`
- `updatedAt`
- `name`
- `birthdate`
- `emailAddress`
- `notes`

```json
[
    {
        "id": 1,
        "createdAt": "2024-05-24T17:20:06+00:00",
        "updatedAt": "2024-05-24T17:20:06+00:00",
        "name": "John Smith",
        "birthdate": "1988-04-15",
        "emailAddress": "jsmith@example.com",
        "notes": "Loves vanilla ice cream."
    },
    {
        "id": 2,
        "createdAt": "2024-05-24T18:22:08+00:00",
        "updatedAt": "2024-05-24T18:22:08+00:00",
        "name": "Mary Jones",
        "birthdate": "1962-08-25",
        "emailAddress": "mary.jones@hotmail.com",
        "notes": "Has three grandchildren."
    }
]
```

#### `POST /customers`
This endpoint will create a new customer record in the database and return that newly created customer. The following validation rules should be applied and an error should be returned if any of them fail:

- `name`: Not Blank, Greater Than 2 Characters, Less Than 129 Characters
- `birthdate`: Nullable, Valid Date
- `emailAddress`: Nullable, Valid Email Address, Less Than 129 Characters
- `notes`: Nullable, Less Than 1025 Characters

```json
{
    "name": "Joe Abbott",
    "birthdate": "1980-01-02",
    "emailAddress": "joeabbott@yahoo.com",
    "notes": null
}
```

```json
{
    "id": 3,
    "createdAt": "2024-05-24T19:11:08+00:00",
    "updatedAt": "2024-05-24T19:11:08+00:00",
    "name": "Joe Abbott",
    "birthdate": "1980-01-02",
    "emailAddress": "joeabbott@yahoo.com",
    "notes": null
}
```

#### `GET /customers/{customerId}`
This endpoint will return a specific customer identified by the `{customerId}` parameter, or a 404 Not Found error if the customer does not exist.

```json
{
    "id": 1,
    "createdAt": "2024-05-24T17:20:06+00:00",
    "updatedAt": "2024-05-24T17:20:06+00:00",
    "name": "John Smith",
    "birthdate": "1988-04-15",
    "emailAddress": "jsmith@example.com",
    "notes": "Loves vanilla ice cream."
}
```
