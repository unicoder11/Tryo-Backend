
<h1 align="center">Tryo Backend</h1>



  

## Endpoint


### Auth Router
.  
**Used for authentication**

| No. | Method | Endpoint                     | Information                      |
| --- | ------ | ---------------------------- | -------------------------------- |
| 1.  | POST   | /auth/signup                 | Used for signup new user.        |
| 2.  |        | /auth/login                  | Used for login into app.         |
| 3.  |        | /auth/forgot                 | Used for forgot password.        |
| 4.  | GET    | /auth/activate/:email/:token | Used for activating new account. |
| 5.  |        | /auth/checkPIN/:pin          | Used for checking PIN .          |
| 6.  | PATCH  | /auth/PIN                    | Used for set PIN / update PIN.   |
| 7.  |        | /auth/reset                  | Used for reseting password.     |
| 8.  | DELETE | /auth/logout/:token          | Used for logout from system.     |
  


### Home Router
**Used for supplying data to home, history, and notification**

| No. | Method | Endpoint            | Information                                                   |
| --- | ------ | ------------------- | ------------------------------------------------------------- |
| 1.  | GET    | /home/getBalance    | Used for get balance user that are logged in.                 |
| 2.  |        | /home/getHistory    | Used for get Transfer , Deposit and Topuut (**IN** or **OUT**) with some range date |
| 3.  |        | /home/getAllInvoice | Used for get **ALL** invoices with some range date            |
  

### Topup Router
**Used for topup any balance to user**

| No. | Method. | Endpoint            | Information                                                    |
| --- | ------- | ------------------- | -------------------------------------------------------------- |
| 1.  | PATCH   | /topup/topupBalance | Used for topup any virtual number matched on user phone number |
 
### Tranfer Router
**Used to all about tranfer feature needed**

| No. | Method | Endpoint             | Information                             |
| --- | ------ | -------------------- | --------------------------------------- |
| 1.  | POST   | /tranfer/newTranfer  | Used to create new tranfer.             |
| 2.  | GET    | /tranfer/search      | Used to search any recipient.           |
| 3.  |        | /tranfer/contactUser | Used to get all contact data.           |
| 4.  |        | /tranfer/details/:id | Used to get details of tranfer history. |

### Deposit Router
**Used to all about tranfer feature needed**

| No. | Method | Endpoint             | Information                             |
| --- | ------ | -------------------- | --------------------------------------- |
| 1.  | POST   | /deposit/newDeposit  | Used to create new tranfer. ( "status" not required )             |
| 2.  | GET    | /deposit/search      | Used to search any recipient.           |
| 3.  |        | /deposit/contactUser | Used to get all contact data.           |
| 4.  |        | /deposit/details/:id | Used to get details of tranfer history. |
| 5.  | PATCH  | /deposit/details/:id | Used to change status (pending, confirmed, canceled) |


### User Router
**Used for any user feature**

| No. | Method | Endpoint             | Information                                                |
| --- | ------ | -------------------- | ---------------------------------------------------------- |
| 1.  | GET    | /user/myProfile      | Used for get all data user that are logged in.             |
| 2.  | PATCH  | /user/changePassword | Used to change password for user.                          |
| 3.  |        | /user/changeInfo     | Used to change any info for example name and phone number. |
| 4.  |        | /user/changePhoto    | Used to change profile picture for user.                   |

## Models

**User model**

```bash
{
  "status": 200,
  "data": [
    {
      "id": 4,
      "name": "Marcos",
      "email" : "hello@example.com",    
      "password" : "hW95UONMYKM7wsP",
      "cpf: : "526.489.495-77",
      "cep" : "44314",
      "cidade": "RJ",
      "phone": "+62895379157496",
      "image": "/images/default.jpg",

    }
  ]
}
```
**Create Deposit**

```bash
{
  {
  "method": "pix",
  "order_id": "Your order id",
  "user_id": "123456",
  "user_name": "Your Name",
  "user_document": "99999999999",
  "user_address": "Your address",
  "user_district": "Your district",
  "user_city": "Your city",
  "user_uf": "UF",
  "user_cep": "99999999",
  "amount": "1.80"
  "status" : "pending"
}
}
```

