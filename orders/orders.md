# Orders REST API

This REST API is being used to get and create orders

## Orders

### Request

`GET /api/orders`

### Headers 
```js
headers: {
    "Content-Type": "application/json",
    "Authorization": "Bearer <jwt token>",
}
```

### Response

##### Success
    Status: 200
    Response Body: { success: true, orders}

#### Fail
    Status: 400
    Response Body: { success: false, error }

    Status: 500
    Response Body: { success: false, error }


`POST /api/orders`

### Body
```js
{
    merchant: merchant._id, // mongodb Object id
    items: [{
        name: String,
        quantity: Number,
        unitPrice: Number,
        description: String,
    }],
    transactions: [{
        paymentMethod: String,
        currency: String,
        paidOn: Date,
        bankName: String,
        IBAN: String,
        amountPaid: Number,
    }],
    installments: [{
        title: String,
        dueDate: Date,
        amount: Number,
        status: String,
        currency: String, 
    }]
}
```

### Headers 
```js
headers: {
    "Content-Type": "application/json",
     "Authorization": "Bearer <jwt token>",
}
```

### Response

##### Success
    Status: 200
    Response Body: { success: true,order}

#### Fail
    Status: 422
    Response Body: { success: false, error }

    Status: 400
    Response Body: { success: false, error }

    Status: 500
    Response Body: { success: false, error }

### Request

`PUT /api/orders`

### Body
```js
{
    contactEmail: String,
    totalPrice : String,
    merchant:String
}
```

### Headers 
```js
headers: {
    "Content-Type": "application/json",
    "Authorization": "Bearer <jwt token>",
}
```

### Response

##### Success
    Status: 200
    Response Body: { success: true,order,case}

#### Fail
    Status: 422
    Response Body: { success: false, error }

    Status: 400
    Response Body: { success: false, error }

    Status: 500
    Response Body: { success: false, error }
