# `paymentGatewayMaintenance`

##### Below is a high level description of the `paymentGatewayMaintenance` API which enables online merchants to accept scheme points as a method of payment. 

##### The online merchant needs to perform a `POST` and upon the receival of the the response redirect his web application to the `GatewayUrl` (output).

##### Request Content Type: `application/json`

# Sample request
```javascript
{
  "MerchantId": "{merchant id}", // provided by Up
  "Status":"ACTIVE",
  "Amount": {amount}, // the amount of the transaction
  "SuccessFallBackUrl": "{success_url}", // the url which the gateway will direct if the transaction is completed
  "FailedFallBackUrl": "www.bing.com",  // the url which the gateway will direct if the transaction fails
  "Runoption": "ADD",
  "institutionID": 6100,
  "institutionPassword": "6100UP",
  "userProfile": "GATEWAY",
  "responseLanguage": "en"
}
```
# Request URL
```https://www.axiomwebservices.com/MeritEChannelsAccessAPI/api/gatewayPaymentMaintenance```

# cURL Sample
```bash
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "MerchantId": "10", \ 
   "Status":"ACTIVE", \ 
   "Amount": 100, \ 
   "SuccessFallBackUrl": "www.google.com", \ 
   "FailedFallBackUrl": "www.bing.com", \ 
   "Runoption": "ADD", \ 
   "institutionID": 6100, \ 
   "institutionPassword": "6100UP", \ 
   "userProfile": "GATEWAY", \ 
   "responseLanguage": "en" \ 
 }' 'https://www.axiomwebservices.com/MeritEChannelsAccessAPI/api/gatewayPaymentMaintenance'
```

# Sample response
```json
{
  "gatewayPaymentMaintenanceOutputs": {
    "SessionId": null,
    "CurrentStatus": null,
    "MappedStatus": null,
    "ExpirationTimestamp": null,
    "MerchantId": null,
    "AcquirerId": null,
    "MerchantNo": null,
    "MerchantDescription": null,
    "MerchantImageUrl": null,
    "Amount": null,
    "SuccessFallBackUrl": null,
    "FailedFallBackUrl": null,
    "GatewayUrl": "https://www.axiomwebservices.com/PartnerPortalGateway/IdentifyCustomer.aspx?m3rt=vfoOAdbVdidkwFY7Esjiy682HUR0Op3NY8JOHSjIcH371y1UVMbXrL0jDAPNhEW44eUAceYOiWTzRkHfWWVBVcft2W5rwOXBHzYcGL5WAhS0L5j5QJaqxPAZA1GmQ/oYXojo7TUr5AL4EXaFfdm9ZlR71DaFDXg0NCHTOXcE9UfcInQLbCYZIcqHED3OWY/S9CvM8JBYGRrBD88Lrjcngw=="
  },
  "returnMessageOutput": {
    "responseCode": "2924",
    "responseMessageType": "I",
    "responseMessage": "INFO 02924 - SESSION ADDED SUCCESSFULLY."
  }
}
```


