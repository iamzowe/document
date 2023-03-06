# CPay Payment Gateway Integration Tutorial

## Workflow 

### Mode 1
![integrate-bank-checkout-cc](https://static.cpay.ltd/images/docs/integrate-bank-checkout-cc.png)

> - API [Create Credit Card Order for Pay-in](https://github.com/cpayfinance/document/blob/main/rest-api-reference/api-transaction.md#create-credit-card-order-for-pay-in)
  will be called with same parameters in `step 1.2`


### Mode 2
![integrate-cpay-checkout-cc](https://static.cpay.ltd/images/docs/integrate-cpay-checkout-cc.png)

> - API [Create Credit Card Order for Pay-in](https://github.com/cpayfinance/document/blob/main/rest-api-reference/api-transaction.md#create-credit-card-order-for-pay-in)
    will be called with same parameters in `step 1.2`


### Mode 3
![integrate-cpay-checkout-crypto1](https://static.cpay.ltd/images/docs/integrate-cpay-checkout-crypto-1.png)

> - API [Create Crypto Order for Pay-in](https://github.com/cpayfinance/document/blob/main/rest-api-reference/api-transaction.md#create-crypto-order-for-pay-in)
    will be called with same parameters in `step 1.2`


### Mode 4
![integrate-cpay-checkout-crypto](https://static.cpay.ltd/images/docs/integrate-cpay-checkout-crypto.png)



## Step 1: Get Credentials
Partners will be provided with the following credentials:
- `MerchantID`
- `SecurityKey`
- `API Host`, see [here](https://github.com/cpayfinance/document/blob/main/rest-api-reference/api-host.md)

## Step 2: Authentication
The request message will be hashed with the API `SecurityKey` using `SHA256` algorithm.

Examples:
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

### Using SDK (_recommend_)


### Using REST APIs


### Using WordPress Plugin

## Q&A
Q1: What are the similarities and differences between `Mode 1` and `Mode 2` ?
> Answers:
>> Similarities:
>> - The same API `Create Credit Card Order for Pay-in` will be called with same parameters in `step 1.2`.
>> - CPay will notify partners in `step 5`, and retry in ten times until receiving `success`.
>
>> Differences:
>> - The page of checkout url was released by the bank in `Mode 1`, however CPay released the page in `Mode 2`


Q2: What are the similarities and differences between `Mode 3` and `Mode 4` ?
> Answers:
>> Similarities:
>> - 都是数字货币收款
>
>> Differences:
>> - Mode 3 先创建订单再进行支付，Mode 4 是直接充值


Q3: How to configure notify url ? 
> Answers:
>> The url can be passed by parameter `callBackURL` or configured in `CPay Merchant System`.  
>> If the url was both configured at the same time, the value passed by parameter `callBackURL` will be used first.

