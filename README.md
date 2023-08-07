[<img src="https://raw.githubusercontent.com/ForgeRock/forgerock-logo-dev/master/Logo-fr-dev.png" align="right" width="220px"/>](https://developer.forgerock.com/)

|Adopted|
|---|
|![license](https://img.shields.io/github/license/ACRA/acra.svg)|
|[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](.github/CODE_OF_CONDUCT.md)|

|Links|
|---|
|[![Wiki](https://img.shields.io/badge/documents-blue?logo=Wikipedia)](https://github.com/SecureApiGateway/SecureApiGateway/wiki)|
|[![Wiki](https://img.shields.io/badge/issues-red?logo=RetroArch)](https://github.com/SecureApiGateway/SecureApiGateway/issues)|

# Secure API Gateway
**_This repository is part of the Secure API Gateway_**

- Top level project - includes wiki and issues

## Endpoints synopsis

### Account and Transaction API

#### 1. Account Access Consents

  * **Overview**
     * The Account Access Consents API is used by an AISP to request an ASPSP to create a new account-access-consent resource, retrieve the status of account-access-consent resource and delete the account-access-consent resource.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | account-access-consents | POST | POST /account-access-consents | Mandatory | accounts | Client Credentials  | No |  | OBReadConsent1 | OBReadConsentResponse1 |
       | 2 | account-access-consents | GET | GET /account-access-consents/{ConsentId} | Mandatory | accounts | Client Credentials | No |  |  | OBReadConsentResponse1 |
       | 3 | account-access-consents | DELETE | DELETE /account-access-consents/{ConsentId} | Mandatory | accounts | Client Credentials | No |  |  |  |    
       


#### 2. Accounts

  * **Overview**
     * The accounts resource is used by an AISP to retrieve full list of accounts and account infromation that the PSU has authorised to access.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | accounts | GET | GET /accounts | Mandatory | accounts | Authorization Code  | No | Pagination |  | OBReadAccount6 |
       | 2 | accounts | GET | GET /accounts/{AccountId} | Mandatory | accounts | Authorization Code | No |  |  | OBReadAccount6 |
       
       
       
#### 3. Balances

  * **Overview**
     * The balances resource is used by an AISP to retrieve in bulk or single account balance information for a specific AccountId for that the PSU has authorised to access.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | balances | GET | GET /accounts/{AccountId}/balances | Mandatory | accounts | Authorization Code  | No |  |  | OBReadBalance1 |
       | 2 | balances | GET | GET /balances | Optional | accounts | Authorization Code | No | Pagination |  | OBReadBalance1 |
       
       
       
#### 4. Transactions

  * **Overview**
     * The transactions resource is used by an AISP to retrieve the transactions for a specific AccountId or to retrieve the transactions in bulk for account(s) that the PSU has authorised to access.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | transactions | GET | GET /accounts/{AccountId}/transactions | Mandatory | accounts | Authorization Code | No | Pagination Filtering |  | OBReadTransaction6 |
       | 2 | transactions | GET | GET /transactions | Optional | accounts | Authorization Code | No | Pagination Filtering |  | OBReadTransaction6 |
       
       
       
#### 5. Beneficiaries

  * **Overview**
     * The beneficiaries resource is used by an AISP to retrieve the account beneficiaries information for a specific AccountId or to retrieve the beneficiaries information in bulk for account(s) that the PSU has authorised to access.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | beneficiaries | GET | GET /accounts/{AccountId}/beneficiaries | Conditional | accounts | Authorization Code | No |  |  | OBReadBeneficiary5 |
       | 2 | beneficiaries | GET | GET /beneficiaries | Optional | accounts | Authorization Code | No | Pagination |  | OBReadBeneficiary5 |
       
       
       
#### 6. Direct Debits

  * **Overview**
     * The direct-debits resource is used by an AISP to retrieve the direct debits for a specific account identified by AccountId or to retrieve direct debits for all accounts that the PSU has consented to.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | direct-debits | GET | GET /accounts/{AccountId}/direct-debits | Conditional | accounts | Authorization Code | No |  |  | OBReadDirectDebit2 |
       | 2 | direct-debits | GET | GET /direct-debits | Optional | accounts | Authorization Code | No | Pagination |  | OBReadDirectDebit2 |
       
       
       
#### 7. Standing Orders

  * **Overview**
     * The standing-orders resource is used by an AISP to retrieve the standing orders for a specific AccountId or to retrieve the standing orders in bulk for all the accounts that the PSU has consented to.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | standing-orders | GET | GET /accounts/{AccountId}/standing-orders | Conditional | accounts | Authorization Code | No |  |  | OBReadStandingOrder6 |
       | 2 | standing-orders | GET | GET /standing-orders | Optional | accounts | Authorization Code | No | Pagination |  | OBReadStandingOrder6 |
       
       
       
#### 8. Products 

  * **Overview**
     * The product resource is used by an AISP to retrieve the account product information for a specific AccountId.

     * The products resource is used by an AISP to retrieve the products for all authorised accounts linked to a specific account-request.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | products | GET | GET /accounts/{AccountId}/product | Conditional | accounts | Authorization Code | No |  |  | OBReadProduct2 |
       | 2 | products | GET | GET /products | Optional | accounts | Authorization Code | No | Pagination |  | OBReadProduct2 |
       
       
       
 #### 9. Offers 

  * **Overview**
     * The offers resource is used by an AISP to retrieve the offers available for a specific AccountId or to retrieve the offers detail in bulk for all accounts that the PSU has consented to.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | offers | GET | GET /accounts/{AccountId}/offers | Conditional | accounts | Authorization Code | No |  |  | OBReadOffer1 |
       | 2 | offers | GET | GET /offers | Optional | accounts | Authorization Code | No | Pagination |  | OBReadOffer1 |
       
       
       
#### 10. Parties 

  * **Overview**
     * The parties resource is used by an AISP to retrieve the details on the account owner(s)/holder(s) and operator(s) for a specific account identified by AccountId.

     * The party resource is used by an AISP to retrieve the details on the account owner/holder for a specific account identified by AccountId:
     
       * In the case of a business, this will be the details of the business. 
       * In the case of a joint account, this will be the party that has given authorisation to the AISP to view the account.
     
     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | parties | GET | GET /accounts/{AccountId}/parties | Conditional | accounts | Authorization Code | No |  |  | OBReadParty3 |
       | 2 | parties | GET | GET /accounts/{AccountId}/party | Conditional | accounts | Authorization Code | No |  |  | OBReadParty2 |
       | 3 | parties | GET | GET /party | Conditional | accounts | Authorization Code | No |  |  | OBReadParty2 |
       
       
       
#### 11. Scheduled Payments 

  * **Overview**
     * The scheduled-payments resource is used by an AISP to retrieve the scheduled payments for a specific account identified by AccountId or to retrieve scheduled payments for all accounts that the PSU has consented to.

     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | scheduled-payments | GET | GET /accounts/{AccountId}/scheduled-payments | Conditional | accounts | Authorization Code | No |  |  | OBReadScheduledPayment3 |
       | 2 | scheduled-payments | GET | GET /scheduled-payments | Optional | accounts | Authorization Code | No | Pagination |  | OBReadScheduledPayment3 |
       
       
       
#### 12. Statements  

  * **Overview**
     * The statements resource is used by an AISP to retrieve the:
     
       * statements information
       * statement information for a StatementId in json and non-json(file) format
       * transactions for a selected StatementId 
     * for a specific account identified by AccountId or retrieve statement information for all accounts that the PSU has consented to.
     
     * This resource description should be read in conjunction with a compatible Account Information Services API Profile.

  *  **Endpoints**
       
     * |  | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Idempotency Key | Parameters | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | 1 | statements | GET | GET /accounts/{AccountId}/statements | Conditional | accounts | Authorization Code | No | Pagination Filtering |  | OBReadStatement2 |
       | 2 | statements | GET | GET /accounts/{AccountId}/statements/{StatementId} | Conditional | accounts | Authorization Code | No |  |  | OBReadStatement2 |
       | 3 | transactions | GET | GET /accounts/{AccountId}/statements/{StatementId}/transactions | Conditional | accounts | Authorization Code | No | Pagination |  | OBReadTransaction6 |
       | 4 | statements | GET | GET /statements | Optional | accounts | Authorization Code | No | Pagination Filtering |  | OBReadStatement2 |
       
       
       
      
### Payment Initiation API

#### 1. Domestic Payments Consents
  
  * **Overview**
     * The Domestic Payments Consent resource is used by a PISP to register an intent to initiate a Domestic Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-payment-consents | POST | POST /domestic-payment-consents | Mandatory | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteDomesticConsent4 | OBWriteDomesticConsentResponse5 |
       | domestic-payment-consents | GET | GET /domestic-payment-consents/{ConsentId} | Mandatory | payments | Client Credentials | Signed Response | No | NA | OBWriteDomesticConsentResponse5 |
       | domestic-payment-consents | GET | GET /domestic-payment-consents/{ConsentId}/funds-confirmation | Mandatory | payments | Authorization Code | Signed Response | No | NA | OBWriteFundsConfirmationResponse1 |
       
       
       
#### 2. Domestic Payments 
  
  * **Overview**
     * The Domestic Payments resource is used by a PISP to initiate a Domestic Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-payments | POST | POST /domestic-payments | Mandatory | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteDomestic2 | OBWriteDomesticResponse5 |
       | domestic-payments | GET | GET /domestic-payments/{DomesticPaymentId} | Mandatory | payments | Client Credentials | Signed Response | No | NA | OBWriteDomesticResponse5 |
       | domestic-payments | GET | GET /domestic-payments/{DomesticPaymentId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       
       
#### 3. Domestic Scheduled Payment Consents 
  
  * **Overview**
     * The Domestic Scheduled Payment Consent resource is used by a PISP to register an intent to initiate a Domestic Scheduled Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-scheduled-payment-consents | POST | POST /domestic-scheduled-payment-consents | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteDomesticScheduledConsent4 | OBWriteDomesticScheduledConsentResponse5 |
       | domestic-scheduled-payment-consents | GET | GET /domestic-scheduled-payment-consents/{ConsentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteDomesticScheduledConsentResponse5 |
       
       
       
#### 4. Domestic Scheduled Payments 
  
  * **Overview**
     * The Domestic Scheduled Payments resource is used by a PISP to initiate a Domestic Scheduled Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-scheduled-payments | POST | POST /domestic-scheduled-payments | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteDomesticScheduled2 | OBWriteDomesticScheduledResponse5 |
       | domestic-scheduled-payments | GET | GET /domestic-scheduled-payments/{DomesticScheduledPaymentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteDomesticScheduledResponse5 |
       | payment-details | GET | GET /domestic-scheduled-payments/{DomesticScheduledPaymentId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       
       
#### 5. Domestic Standing Order Consents
  
  * **Overview**
     * The Domestic Standing Order Consent resource is used by a PISP to register an intent to initiate a Domestic Standing Order.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-standing-order-consents | POST | POST /domestic-standing-order-consents | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteDomesticStandingOrderConsent5 | OBWriteDomesticStandingOrderConsentResponse6 |
       | domestic-standing-order-consents | GET | GET /domestic-standing-order-consents/{ConsentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteDomesticStandingOrderConsentResponse6 |
       
       
       
#### 6. Domestic Standing Orders
  
  * **Overview**
     * The Domestic Standing Orders resource is used by a PISP to initiate a Domestic Standing Order.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-standing-orders | POST | POST /domestic-standing-orders | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteDomesticStandingOrder3 | OBWriteDomesticStandingOrderResponse6 |
       | domestic-standing-orders | GET | GET /domestic-standing-orders/{DomesticStandingOrderId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteDomesticStandingOrderResponse6 |
       | payment-details | GET | GET /domestic-standing-orders/{DomesticStandingOrderId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       
       
#### 7. International Payment Consents
  
  * **Overview**
     * The International Payment Consent resource is used by a PISP to register an intent to initiate an International Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | international-payment-consents | POST | POST /international-payment-consents | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteInternationalConsent5 | OBWriteInternationalConsentResponse6 |
       | international-payment-consents | GET | GET /international-payment-consents/{ConsentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteInternationalConsentResponse6 |
       | international-payment-consents | GET | GET /international-payment-consents/{ConsentId}/funds-confirmation | Mandatory (if resource POST implemented) | payments | Authorization Code | Signed Response | No | NA | OBWriteFundsConfirmationResponse1 |
       
       
       
#### 8. International Payments
  
  * **Overview**
     * The International Payments resource is used by a PISP to initiate an International Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | international-payments | POST | POST /international-payments | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteInternational3 | OBWriteInternationalResponse5 |
       | international-payments | GET | GET /international-payments/{InternationalPaymentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteInternationalResponse5 |
       | payment-details | GET | GET /international-payments/{InternationalPaymentId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       
       
#### 9. International Scheduled Payment Consents
  
  * **Overview**
     * The International Scheduled Payment Consent resource is used by a PISP to register an intent to initiate an International Scheduled Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | international-scheduled-payment-consents | POST | POST /international-scheduled-payment-consents | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteInternationalScheduledConsent5 | OBWriteInternationalScheduledConsentResponse6 |
       | international-scheduled-payment-consents | GET | GET /international-scheduled-payment-consents/{ConsentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteInternationalScheduledConsentResponse6 |
       | international-scheduled-payment-consents | GET | GET /international-scheduled-payment-consents/{ConsentId}/funds-confirmation | Mandatory (if immediate debit supported) | payments | Authorization Code | Signed Response | No | NA | OBWriteFundsConfirmationResponse1 |
       
       
       
#### 10. International Scheduled Payments
  
  * **Overview**
     * The International Scheduled Payments resource is used by a PISP to initiate an International Scheduled Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | international-scheduled-payments | POST | POST /international-scheduled-payments | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteInternationalScheduled3 | OBWriteInternationalScheduledResponse6 |
       | international-scheduled-payments | GET | GET /international-scheduled-payments/{InternationalScheduledPaymentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteInternationalScheduledResponse6 |
       | payment-details | GET | GET /international-scheduled-payments/{InternationalScheduledPaymentId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       

#### 11. International Standing Order Consents
  
  * **Overview**
     * The International Standing Order Consent resource is used by a PISP to register an intent to initiate an International Standing Order.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
     
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | international-standing-order-consents | POST | POST /international-standing-order-consents | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteInternationalStandingOrderConsent6 | OBWriteInternationalStandingOrderConsentResponse7 |
       | international-standing-order-consents | GET | GET /international-standing-order-consents/{ConsentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteInternationalStandingOrderConsentResponse7 |
       
       
       
#### 12. International Standing Orders
  
  * **Overview**
     * The International Standing Orders resource is used by a PISP to initiate an International Standing Order.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | international-standing-orders | POST | POST /international-standing-orders | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteInternationalStandingOrder4 | OBWriteInternationalStandingOrderResponse7 |
       | international-standing-orders | GET | GET /international-standing-orders/{InternationalStandingOrderPaymentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteInternationalStandingOrderResponse7 |
       | payment-details | GET | GET /international-standing-orders/{InternationalStandingOrderPaymentId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       
       
#### 13. File Payment Consents

  * **Overview**
     * The File Payment Consent resource is used by a PISP to register an intent to initiate a File Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | file-payment-consents | POST | POST /file-payment-consents | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | OBWriteFileConsent3 | OBWriteFileConsentResponse4 |
       | file-payment-consents | POST | POST /file-payment-consents/{ConsentId}/file | Conditional | payments | Client Credentials | Signed Request Signed Response | Yes | File | NA |
       | file-payment-consents | GET | GET /file-payment-consents/{ConsentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteFileConsentResponse4 |
       | file-payment-consents | GET | GET /file-payment-consents/{ConsentId}/file | Conditional | payments | Client Credentials | Signed Response | No | NA | File |
       
       
       
#### 14. File Payments

  * **Overview**
     * The File Payment resource is used by a PISP to initiate a File Payment.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**
       
     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | file-payments | POST | POST /file-payments | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBWriteFile2 | OBWriteFileResponse3 |
       | file-payments | GET | GET /file-payments/{FilePaymentId} | Mandatory (if resource POST implemented) | payments | Client Credentials | Signed Response | No | NA | OBWriteFileResponse3 |
       | file-payments | GET | GET /file-payments/{FilePaymentId}/report-file | Conditional | payments | Client Credentials | Signed Response | No | NA | File |
       | payment-details | GET | GET /file-payments/{FilePaymentId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBWritePaymentDetailsResponse1 |
       
       
       
       
### Variable Recurring Payments API

#### 1. Domestic VRP consents

  * **Overview**
     * The Domestic VRP Consents resource is used by a TPP to register a consent to initiate one or more of domestic payments within the control parameters agreed with the PSU.

     * This resource description should be read in conjunction with a compatible Variable Recurring Payments API Profile.
     
     * The PISP must call the end-point with the appropriate scope that they have been assigned. The ASPSP may use the scope to limit to functionality to sweeping or non-sweeping usage of the VRP. 

  *  **Endpoints**

     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-vrp-consents | POST | POST /domestic-vrp-consents | Mandatory | payments | Client Credentials | Signed Request Signed Response | Yes | OBDomesticVRPConsentRequest | OBDomesticVRPConsentResponse |
       | domestic-vrp-consents | GET | GET /domestic-vrp-consents/{ConsentId} | Mandatory | payments | Client Credentials | Signed Response | No | NA | OBDomesticVRPConsentResponse |
       | domestic-vrp-consents | DELETE | DELETE /domestic-vrp-consents/{ConsentId} | Mandatory | payments | Client Credentials | NA | No | NA | None |
       | domestic-vrp-consents | POST | POST /domestic-vrp-consents/{ConsentId}/funds-confirmation | Mandatory | payments | Authorization Code | Signed Request Signed Response | No | OBVRPFundsConfirmationRequest | OBVRPFundsConfirmationResponse |
       
       
       
#### 2. Domestic VRPS

  * **Overview**
     * The Domestic VRPs resource is used by a TPP to initiate a domestic payment, under an authorised VRP Consent.

     * This resource description should be read in conjunction with a compatible Payment Initiation API Profile.

  *  **Endpoints**

     * | Resource | HTTP Operation | Endpoint | Mandatory? | Scope | Grant Type | Message Signing | Idempotency Key | Request Object | Response Object |
       | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
       | domestic-vrps | POST | POST /domestic-vrps | Conditional | payments | Authorization Code | Signed Request Signed Response | Yes | OBDomesticVRPRequest | OBDomesticVRPResponse |
       | domestic-vrps | GET | GET /domestic-vrps/{DomesticVRPId} | Conditional | payments | Client Credentials | Signed Response | No | NA | OBDomesticVRPResponse |
       | domestic-vrps | GET | GET /domestic-vrps/{DomesticVRPId}/payment-details | Optional | payments | Client Credentials | Signed Response | No | NA | OBDomesticVRPRequestDetailResponse |
       
### Funds Confirmation API

#### 1. Funds Confirmation Consents

* **Overview**
    * The Funds Confirmation Consent resource is used by an CBPII to register an intent to confirm funds.

    * This resource description should be read in conjunction with a compatible Confirmation of Funds API Profile.

*  **Endpoints**

    * | Resource                   | HTTP Operation | Endpoint                                        | Mandatory? | Scope              | Grant Type         | Message Signing | Idempotency Key | Request Object              | Response Object                     |
      |----------------------------|----------------|-------------------------------------------------|------------|--------------------|--------------------|-----------------|-----------------|-----------------------------|-------------------------------------|
      | funds-confirmation-consent | POST           | POST /funds-confirmation-consents               | Mandatory  | fundsconfirmations | Client Credentials | No              | No              | OBFundsConfirmationConsent1 | OBFundsConfirmationConsentResponse1 |
      | funds-confirmation-consent | GET            | GET /funds-confirmation-consents/{ConsentId}    | Mandatory  | fundsconfirmations | Client Credentials | No              | No              | NA                          | OBFundsConfirmationConsentResponse1 |
      | funds-confirmation-consent | DELETE         | DELETE /funds-confirmation-consents/{ConsentId} | Mandatory  | fundsconfirmations | Client Credentials | No              | No              | NA                          | NA                                  |


#### 2. Funds Confirmation

* **Overview**
    * The Funds Confirmation resource is used by an CBPII to request to confirm funds are available.

    * This resource description should be read in conjunction with a compatible Confirmation of Funds API Profil

*  **Endpoints**

    * | Resource           | HTTP Operation | Endpoint                  | Mandatory? | Scope              | Grant Type         | Message Signing | Idempotency Key | Request Object       | Response Object              |
      |--------------------|----------------|---------------------------|------------|--------------------|--------------------|-----------------|-----------------|----------------------|------------------------------|
      | funds-confirmation | POST           | POST /funds-confirmations | Mandatory  | fundsconfirmations | Authorization Code | No              | No              | OBFundsConfirmation1 | OBFundsConfirmationResponse1 |
       
       
       
       
       
      

       
       

       
       
       


       

    
