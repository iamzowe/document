# CPay Payment Gateway Integration Tutorial

## Step 1: Get Credentials
Partners will be provided with the following credentials:
- `MerchantID`
- `SecurityKey`
- `API Host`, see [here](https://github.com/cpayfinance/document/blob/main/rest-api-reference/api-host.md)

## Step 2: Authentication
The request message is hashed with the API `SecurityKey` using `SHA256` algorithm.

Example:
```shell
curl https://domain/openapi/v1/getSth?xx=1001&yy=&aa=hello&sign=Vs23424SHW

curl -X POST 'https://domain/openapi/v1/updateSth' -d 'xx=1001&yy=&aa=hello&sign=Vs23424SHW'
```

1. All parameters will be sorted by parameter name and stitched into a string, e.g. `aa=hello&xx=1001`. 
   > Parameter `yy` is ignored here due to its empty value.

2. Append `SecurityKey` to the end of string `aa=hello&xx=1001`, and you will get a new string, e.g. `aa=hello&xx=1001&key=aaaaaaaaaaxxxxxx`

3. Encrypt the string generated in previous step by `SHA256` algorithm.

4. Convert the ciphertext into lower case.

> See a demo [here](https://github.com/cpayfinance/document/blob/main/rest-api-reference/api-signature.md)

## Step 3: Start to Integrate with CPay

### Using WordPress Plugin

If partner want to integrate with CPay using WordPress plugin, please follow: 
- tutorial of [CPay Credit Card Payment Gateway](https://github.com/cpayfinance/cpay-credit-card-gateway-wp)
- tutorial of [CPay Crypto Payment Gateway](https://github.com/cpayfinance/cpay-crypto-gateway-wp)


### Using REST APIs

### Using SDK


