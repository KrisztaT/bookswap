# **Production backend test using Postman**

Postman was extensively used to test the production server routing.

**To open the section and find the corresponding test images, simply click on the triangle icon in front of to the path or the path itself.**

<details>

<summary> GET https://bookswap-server-kt-2962369e5914.herokuapp.com </summary>

### Successful get localhost

![Success home](./home.png)

### Invalid route

![Failure home](./incorrect_route.png)
</details>

<details>

<summary> POST https://bookswap-server-kt-2962369e5914.herokuapp.com/api/user/join </summary>

### Successful join

![Success join](./join_success.png)

### Unsuccessful join as a result of validation errors

![Join short username](./join_short_username.png)
![Join short first name](./join_short_first_name.png)
![Join short password](./join_short_password.png)
![Join existing email](./join_invalid_email.png)

### Unsuccessful join as a result of missing data

![Join missing data](./join_missing_data.png)

### Unsuccessful join as a result of existing data

![Join existing username](./join_username_used.png)

</details>

<details>
<summary> POST https://bookswap-server-kt-2962369e5914.herokuapp.com/api/user/login </summary>

### Successful login

![Success login](./login_successful.png)

### Unsuccessful login as a result of incorrect data

![Login incorrect username](./login_incorrect_username.png)
![Login incorrect password](./login_incorrect_password.png)

### Unsuccessful login as a result of missing data

![Login existing username](./login_missing_username.png)
![Login missing password](./login_missing_password.png)

</details>

<details>

<summary> POST https://bookswap-server-kt-2962369e5914.herokuapp.com/api/listing/ </summary>

### Successful book and listing creation

![Success add](./add_successful.png)

### Unsuccessful book and listing creation as a result of token issues

![Missing token](./add_token_required.png)
![Invalid token](./add_no_authorization.png)

### Unsuccessful book and listing creation as a result of validation errors

![Validation url err](./add_validation_error_url.png)
![Validation page err](./add_validation_error_page.png)
![Validation year err](./add_validation_error_year.png)
![Validation condition err](./add_validation_error_condition.png)

### Unsuccessful book and listing creation as a result of missing data

![Validation url err](./add_missing_data.png)

### Unsuccessful listing creation as a result of exiting listing

![Already added listing](./add_already_added.png)

</details>
<details>

<summary> GET https://bookswap-server-kt-2962369e5914.herokuapp.com/api/listing/ </summary>

### Successful listing

![Success list](./list_successful.png)

### Unsuccessful listing as a result of token issues

![Missing token listing](./list_token_required.png)
![Invalid token listing](./list_no_authorized.png)

</details>
<details>

<summary> GET https://bookswap-server-kt-2962369e5914.herokuapp.com/api/listing/search?title=A game of thrones&condition=good </summary>

### Successful search

![Sucess search](./search_successful.png)

### Unsuccessful search as a result of token issues

![Missing token](./search_token_required.png)
![Invalid token ](./search_no_authorization.png)

### Unsuccessful search as a result of missing title

![Missing title ](./search_title_missing.png)

### Unsuccessful search, no result found

![No result](./search_no_result.png)

</details>

<details>

<summary> https://bookswap-server-kt-2962369e5914.herokuapp.com/api/listing/64c7470537c8555213af0df3 </summary>

### Successful delete

![Sucess delete](./delete_successful.png)

### Unsuccessful delete as a result of token issues

![Missing token](./delete_token_required.png)
![Invalid token ](./delete_no_authorization.png)

### Unsuccessful delete as a result of invalid listingId

![Invalid id ](./delete_invalid_id.png)

</details>

<details>

<summary> https://bookswap-server-kt-2962369e5914.herokuapp.com/api/listing/64c9e88b7e1ca787d3f49660/64c9e88b7e1ca787d3f49667 </summary>

### Successful update

![Sucess update](./update_successful.png)

### Unsuccessful update as a result of token issues

![Missing token](./update_token_required.png)
![Invalid token ](./update_no_authorization.png)

### Unsuccessful search as a result of invalid ids

![Invalid id 1](./update_invalid_book_id.png)
![Invalid id 1](./update_invalid_listing_id.png)

</details>