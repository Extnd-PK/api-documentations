# Approve Installment REST API

This REST API is being used to approve installment

## Approve Installment  

`PUT /api/orders/installments/approve`

### Body
```js
{
  orderId: String, 
  installmentId : String
}
```

### Headers 
```js
headers: {
    "Content-Type": "application/json",
}
```

### Response

##### Success
    Status: 200
    Response Body: { success: true, order }

#### Fail
    Status: 400
    Response Body: { success: false, error }

    Status: 500
    Response Body: { success: false, error }