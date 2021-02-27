---
title: Credgenics API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - Copyright © 2020 Analog Legalhub Technology Solutions Pvt. Ltd. All Rights Reserved.
  # - <a href='https://www.credgenics.com'>Credgenics Website</a>
  # - <a href='https://www.credgenics.com/api/documentation'>Documentation for Lending Companies Here</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Getting Started

Welcome to Credgenics API Documentation. This document will provide instructions on how to quickly integrate Credgenics APIs. Credgenics APIs are based on REST standards. In order to interact with our API, any HTTP client in any programming language can be used.

# Authentication

All the API requests to Credgenics are authenticated via a combination of authentication token and the role of that paticular user who is trying to access the API.

You can request Credgenics for an authentication token and other details. You need to replace {auth_token} in every request with the authentication token that you get from Credgenics.

<aside class="notice">
You must replace <code>{auth_token}</code> with your Authentication Token given by Credgenics.
</aside>

<!-- ************************************* -->
<!-- -----------Lending Recovery API docs-------------------------------------------- -->
<!-- ************************************* -->

# Lending APIs

<!-- GET - Recovery Get loan API------------------------------- -->

## Get Loan API

```python
import requests

url = "https://api.credgenics.com/recovery/loan/{loan_id}"

payload = {}
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request GET 'https://api.credgenics.com/recovery/loan/{loan_id}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.credgenics.com/recovery/loan/{loan_id}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above command returns JSON structured like this:

```json
{
  "loan_details": {
    "loan_id": "2954",
    "loan_type": "Business Loan",
    "product_type": "Arbitration",
    "applicant_name": "Keval Gor",
    "applicant_contact_number": "9706367068",
    "applicant_email": "",
    "applicant_gender": "Male",
    "business_name": "Sathiya Collection",
    "emi_amount": null,
    "loan_tenure": null,
    "applicant_language": "",
    "applicant_occupation": "",
    "applicant_pan_number": "",
    "applicant_cibil_score": null,
    "applicant_dob": null,
    "payment_link": "",
    "client_loan_sanction_date": "2018-02-22",
    "loan_end_date": null,
    "interest_on_loan": null,
    "merchant_name": "",
    "security_type": "",
    "total_loan_amount": 268500,
    "loan_nbfc_name": "HLPL",
    "loan_nbfc_cin": "",
    "tenure_finished": true,
    "backed_by_surety": false,
    "credit_bank_name": "",
    "applicant_address": [
      {
        "applicant_address_type": "Home",
        "applicant_address_text": "Shopno4, Sarpat Gate Bhuj, Bhuj, Gujarat, 370001",
        "applicant_city": "Bhuj",
        "applicant_state": "Gujarat",
        "applicant_pincode": 370001
      }
    ],
    "defaults": [
      {
        "created": "2020-08-14 14:29:02.660409",
        "late_fee": null,
        "expected_emi": 127718,
        "final_status": "Partially Recovered",
        "other_penalty": null,
        "recovery_date": "2020-09-12 00:59:51.418571",
        "payment_method": "Online",
        "date_of_default": "2020-07-05",
        "recovery_method": "",
        "allocation_month": "2020-8-01",
        "amount_recovered": 8500,
        "settlement_amount": 25000,
        "default_emi_number": null,
        "total_claim_amount": 127718,
        "allocation_dpd_value": 91,
        "actual_date_of_default": "2020-05-15",
        "allocation_dpd_bracket": "91-120",
        "client_amount_recovered": null,
        "expected_emi_interest_amount": null,
        "principal_outstanding_amount": null,
        "expected_emi_principal_amount": null
      }
    ],
    "document_details": [],
    "references": [],
    "co_applicant": [],
    "credit_account_number": "",
    "applicant_aadhar_number": "",
    "applicant_monthly_income": null,
    "credit_account_holder_name": "",
    "credit_account_holder_type": ""
  },
  "communication_details": [
    {
      "type_of_comm": "call",
      "comm_dict": {
        "to": "9706367068",
        "from": "8178041121",
        "duration": "0 : 0 : 34",
        "called_to": "applicant",
        "call_start_time": "2020-11-04 17:16:32",
        "call_end_time": "2020-11-04 17:17:06",
        "call_response": "Will pay tomorrow",
        "recording_url": "",
        "applicant_type": "applicant"
      }
    },
    {
      "type_of_comm": "sms",
      "comm_dict": {
        "sms_body": "Hi Keval,\n\nPFA legal notice for the non payment of your outstanding dues to Credgenics as per the terms of the loan agreement. \n\nKindly ignore if the matter has already been settled.\n\nhttps://credgenics.com/notices/930b9ecfee7e?t=64bbec02\n\nThanks and Regards,\n\nAdvocates for HLPL\nAR - Abhishek Gupta\nEmail id: abhishek.gupta1@udaan.com\nPhone number: 9513231633  ",
        "sms_mobile": "9706367068",
        "notice_link": "930b9ecfee7e",
        "delivered_time": "2020-08-15 16:57:31",
        "clicked_time": "2020-08-18 10:55:04.839459",
        "sms_language": "en",
        "message_count": 3,
        "template_name": "Legal Notice Template",
        "character_count": 362,
        "notice_click_count": 2
      }
    }
  ],
  "case_tracking_details": [
    {
      "case_type": "lrn",
      "document_type": "Notice",
      "s3_link": "https://s3-ap-south-1.amazonaws.com/credgenics-cases/production/notice_links/930b9ecfee7e.pdf",
      "data": {}
    },
    {
      "case_type": "lrn",
      "document_type": "Speedpost",
      "data": {
        "events": [
          {
            "date": "05/10/2020",
            "time": "15:27:17",
            "office": "Bhuj HO",
            "description": "Item Delivery Confirmed"
          },
          {
            "date": "05/10/2020",
            "time": "09:17:46",
            "office": "Bhuj HO",
            "description": "Out for Delivery"
          },
          {
            "date": "05/10/2020",
            "time": "08:22:29",
            "office": "Bhuj HO",
            "description": "Item Received"
          },
          {
            "date": "04/10/2020",
            "time": "10:57:04",
            "office": "Bhuj ICH",
            "description": "Item Dispatched"
          },
          {
            "date": "04/10/2020",
            "time": "09:18:22",
            "office": "Bhuj ICH",
            "description": "Item Bagged"
          },
          {
            "date": "04/10/2020",
            "time": "06:17:52",
            "office": "Bhuj ICH",
            "description": "Item Received"
          },
          {
            "date": "03/10/2020",
            "time": "12:30:43",
            "office": "Ahmedabad NSH",
            "description": "Item Dispatched"
          },
          {
            "date": "03/10/2020",
            "time": "11:26:43",
            "office": "Ahmedabad NSH",
            "description": "Item Bagged"
          },
          {
            "date": "03/10/2020",
            "time": "08:40:56",
            "office": "Ahmedabad NSH",
            "description": "Item Received"
          },
          {
            "date": "29/09/2020",
            "time": "17:52:17",
            "office": "Rohini Sector7 SO",
            "description": "Item Dispatched"
          },
          {
            "date": "29/09/2020",
            "time": "17:18:27",
            "office": "Rohini Sector7 SO",
            "description": "Item Bagged"
          },
          {
            "date": "29/09/2020",
            "time": "16:17:42",
            "office": "Rohini Sector7 SO",
            "description": "Item Booked"
          }
        ],
        "booked_at": "Rohini Sector7 SO",
        "article_type": "Inland Speed Post",
        "speedpost_id": "ED670494304IN",
        "applicant_type": "applicant",
        "speedpost_tarrif": "41.30",
        "delivery_location": "Sonipat HO",
        "speedpost_s3_link": "",
        "speedpost_booked_on": "29/09/2020 16:17:42",
        "applicant_address_type": "home",
        "applicant_address_index": 0,
        "speedpost_delivery_status": "Delivered",
        "co_applicant_address_index": -1,
        "speedpost_undelivered_reason": "",
        "speedpost_destination_pincode": "131001",
        "speedpost_delivery_confirmed_on": "05/10/2020 15:27:17"
      }
    }
  ],
  "remarks": [
    {
      "remarks": "(Legal Notice Template ) SMS Sent",
      "created": "2020-11-15 16:57:26",
      "author": "ssingh@credgenics.com"
    },
    {
      "remarks": "Will pay settlement amount tomorrow: Call response , Promise to Pay: Call status , 2020-11-24 - Reminder date",
      "created": "2020-11-23 12:43:11",
      "author": "ssingh@credgenics.com"
    }
  ]
}
```

Use this API to get all the data for a particular loan.

### HTTP Request - GET

`GET https://api.credgenics.com/recovery/loan/{loan_id}`

### Path Parameters

| Parameter | Description |
|-----------|-------------|
| loan_id   | Loan id of the loan |

### Request Headers

| Parameter | Description |
|-----------|-------------|
| authenticationtoken | Auth token given by Credgenics |
| role      | Role of the user |

### Response Structure

| Key | Description |
| ------ | ------ |
| loan_details | JSON object containing information provided at the time of loan insertion and payment related details. For all keys included in this, refer the loan upload API parameters. |
| communication_details | JSON object containing information about all the communications that are performed on the loan. Communication includes call, sms, email and voice messaging.|
| case_tracking_details | JSON object containing information about the legal activities performed on the loan account. It includes case filing, legal notice and physical notice tracking.|
| remarks | JSON object containing all the activities that are performed on the loan account. It provides a snapshot view of the loan account. |

### Response Status Code

<code>200 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.

<!-- POST - Recovery Add loan API------------------------------------------ -->

## Add Loan API

```python
import requests

url = "https://api.credgenics.com/recovery/loan/{loan_id}"

payload = "{\n    \"loan_id\": \"283921\",\n    \"loan_type\": \"Personal Loan\",\n    \"applicant_name\": \"Shri Ram\",\n    \"applicant_dob\": \"1992-03-23\",\n    \"applicant_email\": \"shriram@gmail.com\",\n    \"applicant_gender\": \"Male\",\n    \"applicant_contact_number\": \"9805265926\",\n    \"applicant_monthly_income\": 40000,\n    \"applicant_cibil_score\": 820,\n    \"applicant_occupation\": \"Job\",\n    \"applicant_aadhar_number\": \"235498671293\",\n    \"applicant_language\": \"hi\",\n    \"applicant_pan_number\": \"ADJIY-3516-D\",\n    \"total_loan_amount\": 50000,\n    \"loan_tenure\": 12,\n    \"client_loan_sanction_date\": \"2018-04-06\",\n    \"loan_end_date\": \"2019-04-06\",\n    \"interest_on_loan\": 18,\n    \"tenure_finished\": true,\n    \"security_type\": \"Secured immovable\",\n    \"backed_by_surety\": false,\n    \"loan_nbfc_name\": \"AKARA CAPITAL ADVISORS PVT. LTD.\",\n    \"loan_nbfc_cin\": \"U65191TN1994PLC079235\",\n    \"emi_amount\": 6000,\n    \"product_type\": \"\",\n    \"credit_account_number\": \"11271000005809\",\n    \"credit_account_holder_name\": \"Sri Ram\",\n    \"credit_bank_name\": \"HDFC Bank\",\n    \"credit_account_holder_type\": \"Current\",\n    \"credit_bank_ifsc_code\": \"HDFC0G45B4W\",\n    \"document_details\": [\n        {\n            \"security_mode\": \"NACH\",\n            \"document_number\": \"757493\",\n            \"document_bank_name\": \"HDFC Bank\",\n            \"document_bank_ifsc_code\": \"\",\n            \"document_amount\": 50000,\n            \"document_date\": \"2018-04-10\",\n            \"document_dishonour_date\": \"2018-04-12\",\n            \"document_signature_name\": \"\",\n            \"document_bounce_bank_account_number\": \"\",\n            \"document_bounce_bank_ifsc_code\": \"\",\n            \"document_bounce_charges\": null,\n            \"document_bounce_bank_name\": \"Yes Bank\",\n            \"document_bounce_bank_address\": \"\",\n            \"document_bounce_memo_date\": null,\n            \"reason_of_document_bounce\": \"\"\n        }\n    ],\n    \"business_name\": \"\",\n    \"applicant_address\": [\n        {\n            \"applicant_address_type\": \"Home\",\n            \"applicant_address_text\": \" 395/13 veer dua colony baldev nager\",\n            \"applicant_state\": \"Rajasthan\",\n            \"applicant_city\": \"Jodhpur\",\n            \"applicant_pincode\": 342001\n        }\n    ],\n    \"defaults\": [\n        {\n            \"total_claim_amount\": 113000,\n            \"late_fee\": 59443,\n            \"date_of_default\": \"2019-04-07\",\n            \"expected_emi\": 54000,\n            \"default_emi_number\": 12,\n            \"settlement_amount\": 45000,\n            \"client_amount_recovered\": 0,\n            \"principal_outstanding_amount\": 45000,\n            \"expected_emi_interest_amount\": null,\n            \"expected_emi_principal_amount\": 45000,\n            \"other_penalty\": null\n        }\n    ],\n    \"co_applicant\": [\n        {\n            \"co_applicant_name\": \"Naveen Shekhawat\",\n            \"co_applicant_email\": \"pravinsingh@gmail.com\",\n            \"co_applicant_gender\": \"Male\",\n            \"co_applicant_contact_number\": \"9814274470\",\n            \"co_applicant_dob\": \"1990-06-29\",\n            \"co_applicant_address_text\": \"\",\n            \"co_applicant_state\": \"Rajasthan\",\n            \"co_applicant_city\": \"Alwar\",\n            \"co_applicant_pincode\": 301024\n        }\n    ],\n    \"references\": [\n        {\n            \"relation_with_applicant\": \"Colleague\",\n            \"name\": \"Abhishek Kumar\",\n            \"contact_number\": \"8802913432\"\n        }\n    ],\n    \"merchant_name\": \"Intellipaat\",\n    \"payment_link\": \"https://rzp.io/i/itKAy2q\"\n}"
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request POST 'https://api.credgenics.com/recovery/loan/{loan_id}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "loan_id": "283921",
    "loan_type": "Personal Loan",
    "applicant_name": "Shri Ram",
    "applicant_dob": "1992-03-23",
    "applicant_email": "shriram@gmail.com",
    "applicant_gender": "Male",
    "applicant_contact_number": "9805265926",
    "applicant_monthly_income": 40000,
    "applicant_cibil_score": 820,
    "applicant_occupation": "Job",
    "applicant_aadhar_number": "235498671293",
    "applicant_language": "hi",
    "applicant_pan_number": "ADJIY-3516-D",
    "total_loan_amount": 50000,
    "loan_tenure": 12,
    "client_loan_sanction_date": "2018-04-06",
    "loan_end_date": "2019-04-06",
    "interest_on_loan": 18,
    "tenure_finished": true,
    "security_type": "Secured immovable",
    "backed_by_surety": false,
    "loan_nbfc_name": "AKARA CAPITAL ADVISORS PVT. LTD.",
    "loan_nbfc_cin": "U65191TN1994PLC079235",
    "emi_amount": 6000,
    "product_type": "",
    "credit_account_number": "11271000005809",
    "credit_account_holder_name": "Sri Ram",
    "credit_bank_name": "HDFC Bank",
    "credit_account_holder_type": "Current",
    "credit_bank_ifsc_code": "HDFC0G45B4W",
    "document_details": [
        {
            "security_mode": "NACH",
            "document_number": "757493",
            "document_bank_name": "HDFC Bank",
            "document_bank_ifsc_code": "",
            "document_amount": 50000,
            "document_date": "2018-04-10",
            "document_dishonour_date": "2018-04-12",
            "document_signature_name": "",
            "document_bounce_bank_account_number": "",
            "document_bounce_bank_ifsc_code": "",
            "document_bounce_charges": null,
            "document_bounce_bank_name": "Yes Bank",
            "document_bounce_bank_address": "",
            "document_bounce_memo_date": null,
            "reason_of_document_bounce": ""
        }
    ],
    "business_name": "",
    "applicant_address": [
        {
            "applicant_address_type": "Home",
            "applicant_address_text": " 395/13 veer dua colony baldev nager",
            "applicant_state": "Rajasthan",
            "applicant_city": "Jodhpur",
            "applicant_pincode": 342001
        }
    ],
    "defaults": [
        {
            "total_claim_amount": 113000,
            "late_fee": 59443,
            "date_of_default": "2019-04-07",
            "expected_emi": 54000,
            "default_emi_number": 12,
            "settlement_amount": 45000,
            "client_amount_recovered": 0,
            "principal_outstanding_amount": 45000,
            "expected_emi_interest_amount": null,
            "expected_emi_principal_amount": 45000,
            "other_penalty": null
        }
    ],
    "co_applicant": [
        {
            "co_applicant_name": "Naveen Shekhawat",
            "co_applicant_email": "pravinsingh@gmail.com",
            "co_applicant_gender": "Male",
            "co_applicant_contact_number": "9814274470",
            "co_applicant_dob": "1990-06-29",
            "co_applicant_address_text": "",
            "co_applicant_state": "Rajasthan",
            "co_applicant_city": "Alwar",
            "co_applicant_pincode": 301024
        }
    ],
    "references": [
        {
            "relation_with_applicant": "Colleague",
            "name": "Abhishek Kumar",
            "contact_number": "8802913432"
        }
    ],
    "merchant_name": "Intellipaat",
    "payment_link": "https://rzp.io/i/itKAy2q"
}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"loan_id":"283921","loan_type":"Personal Loan","applicant_name":"Shri Ram","applicant_dob":"1992-03-23","applicant_email":"shriram@gmail.com","applicant_gender":"Male","applicant_contact_number":"9805265926","applicant_monthly_income":40000,"applicant_cibil_score":820,"applicant_occupation":"Job","applicant_aadhar_number":"235498671293","applicant_language":"hi","applicant_pan_number":"ADJIY-3516-D","total_loan_amount":50000,"loan_tenure":12,"client_loan_sanction_date":"2018-04-06","loan_end_date":"2019-04-06","interest_on_loan":18,"tenure_finished":true,"security_type":"Secured immovable","backed_by_surety":false,"loan_nbfc_name":"AKARA CAPITAL ADVISORS PVT. LTD.","loan_nbfc_cin":"U65191TN1994PLC079235","emi_amount":6000,"product_type":"","credit_account_number":"11271000005809","credit_account_holder_name":"Sri Ram","credit_bank_name":"HDFC Bank","credit_account_holder_type":"Current","credit_bank_ifsc_code":"HDFC0G45B4W","document_details":[{"security_mode":"NACH","document_number":"757493","document_bank_name":"HDFC Bank","document_bank_ifsc_code":"","document_amount":50000,"document_date":"2018-04-10","document_dishonour_date":"2018-04-12","document_signature_name":"","document_bounce_bank_account_number":"","document_bounce_bank_ifsc_code":"","document_bounce_charges":null,"document_bounce_bank_name":"Yes Bank","document_bounce_bank_address":"","document_bounce_memo_date":null,"reason_of_document_bounce":""}],"business_name":"","applicant_address":[{"applicant_address_type":"Home","applicant_address_text":" 395/13 veer dua colony baldev nager","applicant_state":"Rajasthan","applicant_city":"Jodhpur","applicant_pincode":342001}],"defaults":[{"total_claim_amount":113000,"late_fee":59443,"date_of_default":"2019-04-07","expected_emi":54000,"default_emi_number":12,"settlement_amount":45000,"client_amount_recovered":0,"principal_outstanding_amount":45000,"expected_emi_interest_amount":null,"expected_emi_principal_amount":45000,"other_penalty":null}],"co_applicant":[{"co_applicant_name":"Naveen Shekhawat","co_applicant_email":"pravinsingh@gmail.com","co_applicant_gender":"Male","co_applicant_contact_number":"9814274470","co_applicant_dob":"1990-06-29","co_applicant_address_text":"","co_applicant_state":"Rajasthan","co_applicant_city":"Alwar","co_applicant_pincode":301024}],"references":[{"relation_with_applicant":"Colleague","name":"Abhishek Kumar","contact_number":"8802913432"}],"merchant_name":"Intellipaat","payment_link":"https://rzp.io/i/itKAy2q"});

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.credgenics.com/recovery/loan/{loan_id}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above code returns JSON structured like this:

```json
{
  "output": "Loan added successfully",
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to add new Loan / EMI to the data. Goes without saying your data is secure with us. :)

### HTTP Request - POST

`POST https://api.credgenics.com/recovery/loan/{loan_id}`

### Path Parameters

| Parameter | Description |
|-----------|-------------|
| loan_id   | Loan id of the loan |

### Request Headers

| Parameter | Description |
|-----------|-------------|
| authenticationtoken | Auth token assigned by Credgenics |
| role | Role of the user |

### Request Body Parameters

| Key name | Type | Required | Default Value | Description |
|----------|------|----------|---------------|-------------|
| loan_id  | string | True | - | Loan id of the loan |
| client_customer_id | string | False | - | Customer id of the applicant |
| loan_type | string | True | - | Loan type of the loan. Eg: Personal Loan, Business Loan, Vehicle Loan, etc. |
| applicant_name | string | True | - | Name of the applicant |
| applicant_email | string | False | "" | Email id of the applicant |
| applicant_contact_number | string | False | "" | Contact Number of the applicant |
| applicant_gender | string | False | "" | Gender of the applicant |
| applicant_dob | date | False | None | Date of birth of the applicant. Eg - "1998-06-22" |
| applicant_monthly_income | integer | False | None | Monthly income of the applicant |
| applicant_cibil_score | integer | False | None | Cibil score of the applicant |
| applicant_occupation | string | False | "" | Occupation of the applicant |
| applicant_aadhar_number | string | False | "" | Aadhar number of the applicant |
| applicant_pan_number | string | False | "" | PAN number of the applicant |
| applicant_language | string | False | "" | Language of the applicant. Eg - "en" - English, "hi" - Hindi, "bn" - Bengali, "gu" - Gujarati, "ml" - Malayalam, "mr" - Marathi, "pa" - Punjabi, "te" - telugu, "ta" - Tamil, "kn" - Kannada |
| total_loan_amount | integer | True | - | Loan amount of the loan |
| loan_tenure | integer | False | None | Tenure of the  loan in months |
| client_loan_sanction_date | date | False | None | Sanction date  of the loan. Eg - "2020-01-23" |
| loan_end_date | date | False | None | End date of the loan. Eg - "2021-11-23" |
| interest_on_loan | float | False | None | Interest on the loan amount |
| tenure_finished | boolean | False | None | Is the tenure of the loan finished? Choices - True, False |
| security_type | string | False | "" | Is the loan secured and if yes, then what is the security type? Choices - Secured, Movable, Secured Immovable, Unsecured |
| backed_by_security | boolean | False | None | Is there a guarantor for the loan? Choices - True, False |
| loan_nbfc_name | string | False | "" | NBFC name |
| loan_nbfc_cin | string | False | "" | NBFC CIN |
| emi_amount | integer | False | None | Single EMI amount of the loan |
| product_type | string | False | "" | Further classification of the loan_type. Eg - 4-wheeler loan, 2-wheeler Loan, Overdraft loan, Term Loan etc. |
| credit_account_number | string | False | "" | Account number of the borrower in which he/she recieved the loan amount. Eg - "0000012835" |
| credit_account_holder_name | string | False | "" | Name of the account holder |
| credit_account_holder_type | string | False | "" | Account type of the credit bank account |
| credit_bank_name | string | False | "" | Bank name of the credit card |
| credit_bank_ifsc_code | string | False | "" | IFSC code of credit bank |
| business_name | string | False | "" | Applicant business name |
| merchant_name | string | False | "" | Merchant name |
| payment_link | string | False | "" | Payment link |
| channel_partner | string | False | "" | Channel Partner |
| loan_regional_manager_name | string | False | "" | Name of the loan regional manager |
| loan_regional_manager_contact_number | string | False | "" | Contact number of the loan regional manager |
| loan_regional_manager_contact_email | string | False | "" | Contact email id of the loan regional manager |
| ***Document Keys*** |
| security_mode | string | False | "" | What is the security for the loan ? Eg - NACH, ECS, ENACH, PDC, Others (Two wheeler, Fou wheeler, house) etc. |
| document_number | string | False | "" | Document number of the security_mode document Eg. Cheque Number, ECS number etc. |
| document_bank_name | string | False | "" | security mode document bank name. Eg. Cheque bank name |
| document_bank_ifsc_code | string | False | "" | IFSC code of the document bank |
| document_amount | integer | False | None | Amount mentioned on the security_mode document. Eg. Cheque amount |
| document_date | date | False | None | Execution date security_mode document. Eg. Cheque date |
| document_dishonour_date | date | False | None | Dishonour date of the security_mode document. Eg. Cheque dishonour date |
| document_signature_name | string | False | "" | Name of the Signee on the security_mode document. Eg. Signee name on the Cheque |
| document_bounce_bank_account_number | string | False | "" | Account number of the account in which document was bounced |
| document_bounce_charges | integer | False | None | Document bounce charges |
| document_bounce_bank_name | string | False | "" | Bank name in which the security_mode document was bounced |
| document_bounce_bank_ifsc_code | string | False | "" | IFSC code of the bank in which document was bounced |
| document_bounce_bank_address | string | False | "" | Address of the bank in which document was bounced |
| document_bounce_memo_date | date | False | None | Date of document bounce memo", "variable_name |
| reason_of_document_bounce | string | False | "" | Reason behind the security_mode document bounce. Eg. Insufficient balance |
| document_micr | string | False | "" | 9 digit Document MICR Code |
| document_presented_in_account | string | False | "" | Account in which document is presented |
| document_presented_zone | string | False | "" | Zone in which document is presented |
| document_bounce_memo_branch_address | string | False | "" | Address of the document bounce memo branch |
| ***Address Keys*** |
| applicant_address_type | string | True | - | Type of the address. Choice - Home, Business, Office.
| applicant_address_text | text | True | - | Address of the applicant |
| applicant_state | string | True | - | State of the applicant |
| applicant_city | string | True | - | City of the applicant |
| applicant_pincode | integer | True | - | Pincode of the applicant |
| ***Default Keys*** |
| total_claim_amount | integer | True | None | Total claim amount of the loan |
| late_fee | integer | True | None | Late fee of the loan |
| date_of_default | date | True | None | Default date of the loan |
| expected_emi | integer | True | None | Expected emi amount of the loan |
| default_emi_number | integer | True | None | Default EMI number |
| settlement_amount | integer | True | None | Settlement amount of the loan |
| client_amount_recovered | integer | True | None | Amount recovered by thr client |
| principal_outstanding_amount | integer | True | None | Principal outstanding amount of the loan |
| expected_emi_interest_amount | integer | True | None | Interest amount of the loan |
| expected_emi_principal_amount | integer | True | None | Principal amount of the expected EMI |
| other_penalty | integer | True | None | Any other penalty amount |
| ***Reference Keys*** |
| relation_with_applicant | string | False | "" | Referenced person's relation with applicant |
| name | string | False | "" | Name of the referenced person |
| contat_number | string | False | "" | Contact number of the referenced person |
| ***Coapplicant Keys*** |
| co_applicant_name | string | False | "" | Name of the co-applicant |
| co_applicant_email | string | False | "" | Email id of the applicant |
| co_applicant_contact_number | string | False | "" | Contact number of the co-applicant |
| co_applicant_gender | string | False | "" | Gender of the co-applicant |
| co_applicant_dob | date | False | None | Date of birth of the co-applicant |
| co_applicant_address_text | text | False |  "" | Address of the co-applicant |
| co_applicant_state | string | False | "" | State of the co-applicant |
| co_applicant_city | string | False | "" | City of the co-applicant |
| co_applicant_pincode | integer | False | None | Pincode of the co-applicant |

### Response Status Code

<code>201 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.


<!-- PATCH - Recovery Update loan API----------------------------------- -->

## Update Loan API

```python
import requests

url = "https://api.credgenics.com/recovery/loan/{loan_id}"

payload = "{\n    \"total_loan_amount\": 60000\n}"
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}',
  'Content-Type': 'application/json'
}

response = requests.request("PATCH", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request PATCH 'https://api.credgenics.com/recovery/loan/{loan_id}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "total_loan_amount": 60000
}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"total_loan_amount":60000});

var requestOptions = {
  method: 'PATCH',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.credgenics.com/recovery/loan/{loan_id}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above code returns JSON structured like this:

```json
{
  "output": "Loan successfully updated",
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to update the details of a particular loan.

### HTTP Request - PATCH

`PATCH https://api.credgenics.com/recovery/loan/{loan_id}`

### Path Parameters

| Parameter | Description |
|-----------|-------------|
| loan_id | Loan id of the loan |

### Request Headers

| Parameter | Description |
|-----------|-------------|
| authenticationtoken | Auth token given by Credgenics |
| role | Role of the user |

<aside class="notice">
Request Body Parameters of this API are same as the parameters of Lending Add Loan API, so refer to the parameters of the Add Loan API to know the details related to the parameters of this API.
</aside>

### Response Status Code

<code>200 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.

## Update Payment API

```python
import requests

url = "https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}"

payload = "{\n    \"final_status\": \"Partially Recovered\",\n    \"amount_recovered\": 3450,\n    \"payment_method\": \"Online\",\n    \"date_of_default\": \"2020-01-23\"\n}"
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}',22
  'Content-Type': 'application/json'
}

response = requests.request("PATCH", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request PATCH 'https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "final_status": "Partially Recovered",
    "amount_recovered": 3450,
    "payment_method": "Online",
    "date_of_default": "2020-01-23"
}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"final_status":"Partially Recovered","amount_recovered":3450,"payment_method":"Online","date_of_default":"2020-01-23"});

var requestOptions = {
  method: 'PATCH',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above code returns JSON structured like this:

```json
{
  "output": "Data updated successfully",
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to update the payment details of a customer.

### HTTP Requests - PATCH

`PATCH https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}`

### Path Parameters

| Parameter | Description |
| ------ | ------ |
| loan_id | Loan id of the recovered loan |
| allocation_month | Allocation month of the recovered loan. Eg - "2021-2-01" |

<aside class="notice">
NOTE: Date will always be '01' and month should always be without leading '0' in <code>allocation_month</code> key
</aside>

### Request Headers

| Parameter | Description |
| ------ | ------ |
| authenticationtoken | The authentication token assigned to you by Credgenics |
| role | The role of the user |
| Content-Type | "application/json" |

### Request Body Parameters

| Key Name | Type | Required |Description |
| ------ | ------ | ------ | ------ |
| final_status | string | True | The status of the loan. Choices - Partially Recovered, Closed |
| recovery_method | string | False | Recovery method of the loan. Choices - Communications, Field Collection, Legal |
| payment_method | string | True | Method by which the payment has been made. Choices - Cash, Online, Cheque, Application, Bank Account Transfer, Payment Link. |
| date_of_default | date | True  | Date of default of the loan ( Required only if final_status is Partially Recovered ) |
| closure_with | string | False | Choices for closure - NOC, Settlement |
| payment_reference_number | string | False | Payment Reference Number |
| payment_mode | string | False | Mode of payment |

### Response Status Code

<code>200 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.

<!-- ************************************** -->
<!-- ---------CREDIT LINE API DOCS---------------------------------------------- -->
<!-- ************************************** -->

# Credit Line APIs

<!-- CREDIT LINE - Get loan API----------------------- -->

## Get Loan API

```python
import requests

url = "https://api.credgenics.com/recovery/loan/{loan_id}"

payload = {}
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request GET 'https://api.credgenics.com/recovery/loan/{loan_id}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");

var requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow",
};

fetch(
  "https://api.credgenics.com/recovery/loan/{loan_id}",
  requestOptions
)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "output": {
    "applicant_details": {
      "client_customer_id": "189004",
      "defaults": [
        {
          "final_status": "Initiated",
          "allocation_month": "2021-1-01",
          "amount_recovered": 0,
          "settlement_amount": null
        },
        {
          "final_status": "Initiated",
          "allocation_month": "2021-2-01",
          "amount_recovered": 3550,
          "settlement_amount": 45000
        }
      ],
      "loan_type": "Personal Loan",
      "references": [
        {
          "name": "Shri Ram",
          "contact_number": "9999999999",
          "relation_with_applicant": "Colleague"
        }
      ],
      "co_applicant": [
        {
          "co_applicant_dob": "1990-06-29",
          "co_applicant_city": "Alwar",
          "co_applicant_name": "Naveen Shekhawat",
          "co_applicant_email": "pravin@gmail.com",
          "co_applicant_state": "Rajasthan",
          "co_applicant_gender": "Male",
          "co_applicant_pincode": 301024,
          "co_applicant_address_text": "",
          "co_applicant_contact_number": "9614294470"
        }
      ],
      "payment_link": "",
      "product_type": "Payday personal",
      "applicant_dob": "1992-03-23",
      "business_name": "ABC PVT. LTd.",
      "engine_number": "",
      "loan_end_date": "2019-04-06",
      "loan_nbfc_cin": "U65191TN1994PLC078035",
      "merchant_name": "Intellipaat",
      "security_type": "Secured immovable",
      "applicant_name": "Sri Ram",
      "chassis_number": "",
      "loan_nbfc_name": "AKARA CAPITAL ADVISORS PVT. LTD.",
      "make_and_model": "",
      "applicant_email": "shriram@gmail.com",
      "applicant_gender": "Male",
      "backed_by_surety": false,
      "credit_bank_name": "HDFC Bank",
      "document_details": [
        {
            "security_mode": "NACH",
            "document_number": "757493",
            "document_bank_name": "HDFC Bank",
            "document_bank_ifsc_code": "",
            "document_amount": 50000,
            "document_date": "2018-04-10",
            "document_dishonour_date": "2018-04-12",
            "document_signature_name": "",
            "document_bounce_bank_account_number": "",
            "document_bounce_bank_ifsc_code": "",
            "document_bounce_charges": null,
            "document_bounce_bank_name": "Yes Bank",
            "document_bounce_bank_address": "",
            "document_bounce_memo_date": null,
            "reason_of_document_bounce": ""
        }
      ],
      "applicant_address": [
        {
          "applicant_city": "Jodhpur",
          "applicant_state": "Rajasthan",
          "applicant_pincode": 342001,
          "applicant_address_text": "395/13 Veer Dua Colony Baldev Nager",
          "applicant_address_type": "Home"
        }
      ],
      "applicant_language": "hi",
      "applicant_occupation": "Job",
      "applicant_pan_number": "",
      "applicant_cibil_score": 820,
      "credit_account_number": "",
      "credit_bank_ifsc_code": "HDFC0G45B4W",
      "applicant_aadhar_number": "",
      "applicant_contact_number": "9999999999",
      "applicant_monthly_income": 40000,
      "credit_account_holder_name": "Sri Ram",
      "credit_account_holder_type": "Current",
      "loan_regional_manager_name": "",
      "vehicle_registration_number": "",
      "loan_regional_manager_contact_email": "",
      "loan_regional_manager_contact_number": ""
    },
    "transactions_details": [
      {
        "transaction_id": "283921",
        "data": {
          "defaults": [
            {
              "created": "2021-02-14 20:22:41.889461",
              "late_fee": 59443,
              "upload_date": null,
              "closure_with": "",
              "expected_emi": 54000,
              "final_status": "Partially Recovered",
              "payment_mode": "",
              "other_penalty": null,
              "recovery_date": "2021-02-26 13:07:22.248235",
              "payment_method": "Online",
              "date_of_default": "2020-01-23",
              "recovery_method": "",
              "allocation_month": "2021-2-01",
              "amount_recovered": 3450,
              "reference_number": "",
              "default_emi_number": 12,
              "total_claim_amount": 113000,
              "allocation_dpd_value": 679,
              "actual_date_of_default": "2019-04-07",
              "allocation_dpd_bracket": "180+",
              "client_amount_recovered": 0,
              "expected_emi_interest_amount": null,
              "principal_outstanding_amount": 45000,
              "expected_emi_principal_amount": 45000
            }
          ],
          "emi_amount": 6000,
          "loan_tenure": 12,
          "loan_end_date": "2019-04-06",
          "transaction_id": "283921",
          "tenure_finished": true,
          "interest_on_loan": 18,
          "total_loan_amount": 50000,
          "client_loan_sanction_date": "2018-04-06"
        }
      },
      {
        "transaction_id": "18372",
        "data": {
          "defaults": [
            {
              "created": "2021-01-27 18:57:11.514467",
              "late_fee": 1000,
              "upload_date": "",
              "expected_emi": 10001,
              "final_status": "Initiated",
              "other_penalty": null,
              "date_of_default": "2020-03-02",
              "allocation_month": "2021-1-01",
              "amount_recovered": 0,
              "default_emi_number": 4,
              "total_claim_amount": 9000,
              "allocation_dpd_value": 331,
              "actual_date_of_default": "2020-03-02",
              "allocation_dpd_bracket": "180+",
              "client_amount_recovered": null,
              "expected_emi_interest_amount": 2000,
              "principal_outstanding_amount": 1000,
              "expected_emi_principal_amount": 9000
            }
          ],
          "emi_amount": 1000,
          "loan_tenure": 11,
          "loan_end_date": "2020-03-02",
          "transaction_id": "283920",
          "tenure_finished": true,
          "interest_on_loan": 12,
          "total_loan_amount": 902929,
          "client_loan_sanction_date": "2020-01-29"
        }
      },
    ],
    "communication_details": [
    {
      "type_of_comm": "call",
      "comm_dict": {
        "to": "9706367068",
        "from": "8178041121",
        "duration": "0 : 0 : 34",
        "called_to": "applicant",
        "call_start_time": "2020-11-04 17:16:32",
        "call_end_time": "2020-11-04 17:17:06",
        "call_response": "Will pay tomorrow",
        "recording_url": "",
        "applicant_type": "applicant"
      }
    },
    {
      "type_of_comm": "sms",
      "comm_dict": {
        "sms_body": "Hi Keval,\n\nPFA legal notice for the non payment of your outstanding dues to Credgenics as per the terms of the loan agreement. \n\nKindly ignore if the matter has already been settled.\n\nhttps://credgenics.com/notices/930b9ecfee7e?t=64bbec02\n\nThanks and Regards,\n\nAdvocates for HLPL\nAR - Abhishek Gupta\nEmail id: abhishek.gupta1@udaan.com\nPhone number: 9513231633  ",
        "sms_mobile": "9706367068",
        "notice_link": "930b9ecfee7e",
        "delivered_time": "2020-08-15 16:57:31",
        "clicked_time": "2020-08-18 10:55:04.839459",
        "sms_language": "en",
        "message_count": 3,
        "template_name": "Legal Notice Template",
        "character_count": 362,
        "notice_click_count": 2
      }
    }
  ],
    "case_tracking_details": [
    {
      "case_type": "lrn",
      "document_type": "Notice",
      "s3_link": "https://s3-ap-south-1.amazonaws.com/credgenics-cases/production/notice_links/930b9ecfee7e.pdf",
      "data": {}
    },
    {
      "case_type": "lrn",
      "document_type": "Speedpost",
      "data": {
        "events": [
          {
            "date": "05/10/2020",
            "time": "15:27:17",
            "office": "Bhuj HO",
            "description": "Item Delivery Confirmed"
          },
          {
            "date": "05/10/2020",
            "time": "09:17:46",
            "office": "Bhuj HO",
            "description": "Out for Delivery"
          },
          {
            "date": "05/10/2020",
            "time": "08:22:29",
            "office": "Bhuj HO",
            "description": "Item Received"
          },
          {
            "date": "04/10/2020",
            "time": "10:57:04",
            "office": "Bhuj ICH",
            "description": "Item Dispatched"
          },
          {
            "date": "04/10/2020",
            "time": "09:18:22",
            "office": "Bhuj ICH",
            "description": "Item Bagged"
          },
          {
            "date": "04/10/2020",
            "time": "06:17:52",
            "office": "Bhuj ICH",
            "description": "Item Received"
          },
          {
            "date": "03/10/2020",
            "time": "12:30:43",
            "office": "Ahmedabad NSH",
            "description": "Item Dispatched"
          },
          {
            "date": "03/10/2020",
            "time": "11:26:43",
            "office": "Ahmedabad NSH",
            "description": "Item Bagged"
          },
          {
            "date": "03/10/2020",
            "time": "08:40:56",
            "office": "Ahmedabad NSH",
            "description": "Item Received"
          },
          {
            "date": "29/09/2020",
            "time": "17:52:17",
            "office": "Rohini Sector7 SO",
            "description": "Item Dispatched"
          },
          {
            "date": "29/09/2020",
            "time": "17:18:27",
            "office": "Rohini Sector7 SO",
            "description": "Item Bagged"
          },
          {
            "date": "29/09/2020",
            "time": "16:17:42",
            "office": "Rohini Sector7 SO",
            "description": "Item Booked"
          }
        ],
        "booked_at": "Rohini Sector7 SO",
        "article_type": "Inland Speed Post",
        "speedpost_id": "ED670494304IN",
        "applicant_type": "applicant",
        "speedpost_tarrif": "41.30",
        "delivery_location": "Sonipat HO",
        "speedpost_s3_link": "",
        "speedpost_booked_on": "29/09/2020 16:17:42",
        "applicant_address_type": "home",
        "applicant_address_index": 0,
        "speedpost_delivery_status": "Delivered",
        "co_applicant_address_index": -1,
        "speedpost_undelivered_reason": "",
        "speedpost_destination_pincode": "131001",
        "speedpost_delivery_confirmed_on": "05/10/2020 15:27:17"
      }
    }
  ],
  "remarks": [
    {
      "remarks": "(Legal Notice Template ) SMS Sent",
      "created": "2020-11-15 16:57:26",
      "author": "ssingh@credgenics.com"
    },
    {
      "remarks": "Will pay settlement amount tomorrow: Call response , Promise to Pay: Call status , 2020-11-24 - Reminder date",
      "created": "2020-11-23 12:43:11",
      "author": "ssingh@credgenics.com"
    }
  ]
  },
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to retrieve all details of a particular loan

### HTTP Request - GET

`GET https://api.credgenics.com/recovery/loan/{loan_id}`


### Path Parameters

| Parameter        | Description                        |
| ---------------- | ---------------------------------- |
| loan_id          | Loan id of the loan                |

### Request Headers

| Parameter           | Description                    |
| ------------------- | ------------------------------ |
| authenticationtoken | Auth token given by Credgenics |
| role                | Role of the user               |

### Response Status Code

<code>200 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.

<!-- <aside class="info">
Remember — {auth_token} is an authentication token
</aside> -->

<!-- CREDIT LINE - ADD loan API---------------------------- -->

## Add Loan API 

```python
import requests

url = "https://api.credgenics.com/recovery/loan/{loan_id}"

payload = "{\n    \"client_customer_id\": \"189004\",\n    \"loan_id\": \"283921\",\n    \"loan_type\": \"Personal Loan\",\n    \"applicant_name\": \"Shri Ram\",\n    \"applicant_dob\": \"1992-03-23\",\n    \"applicant_email\": \"shriram@gmail.com\",\n    \"applicant_gender\": \"Male\",\n    \"applicant_contact_number\": \"9805265926\",\n    \"applicant_monthly_income\": 40000,\n    \"applicant_cibil_score\": 820,\n    \"applicant_occupation\": \"Job\",\n    \"applicant_aadhar_number\": \"235498671293\",\n    \"applicant_language\": \"hi\",\n    \"applicant_pan_number\": \"ADJIY-3516-D\",\n    \"total_loan_amount\": 50000,\n    \"loan_tenure\": 12,\n    \"client_loan_sanction_date\": \"2018-04-06\",\n    \"loan_end_date\": \"2019-04-06\",\n    \"interest_on_loan\": 18,\n    \"tenure_finished\": true,\n    \"security_type\": \"Secured immovable\",\n    \"backed_by_surety\": false,\n    \"loan_nbfc_name\": \"AKARA CAPITAL ADVISORS PVT. LTD.\",\n    \"loan_nbfc_cin\": \"U65191TN1994PLC079235\",\n    \"emi_amount\": 6000,\n    \"product_type\": \"\",\n    \"credit_account_number\": \"11271000005809\",\n    \"credit_account_holder_name\": \"Sri Ram\",\n    \"credit_bank_name\": \"HDFC Bank\",\n    \"credit_account_holder_type\": \"Current\",\n    \"credit_bank_ifsc_code\": \"HDFC0G45B4W\",\n    \"document_details\": [\n        {\n            \"security_mode\": \"NACH\",\n            \"document_number\": \"757493\",\n            \"document_bank_name\": \"HDFC Bank\",\n            \"document_bank_ifsc_code\": \"\",\n            \"document_amount\": 50000,\n            \"document_date\": \"2018-04-10\",\n            \"document_dishonour_date\": \"2018-04-12\",\n            \"document_signature_name\": \"\",\n            \"document_bounce_bank_account_number\": \"\",\n            \"document_bounce_bank_ifsc_code\": \"\",\n            \"document_bounce_charges\": null,\n            \"document_bounce_bank_name\": \"Yes Bank\",\n            \"document_bounce_bank_address\": \"\",\n            \"document_bounce_memo_date\": null,\n            \"reason_of_document_bounce\": \"\"\n        }\n    ],\n    \"business_name\": \"\",\n    \"applicant_address\": [\n        {\n            \"applicant_address_type\": \"Home\",\n            \"applicant_address_text\": \" 395/13 veer dua colony baldev nager\",\n            \"applicant_state\": \"Rajasthan\",\n            \"applicant_city\": \"Jodhpur\",\n            \"applicant_pincode\": 342001\n        }\n    ],\n    \"defaults\": [\n        {\n            \"total_claim_amount\": 113000,\n            \"late_fee\": 59443,\n            \"date_of_default\": \"2019-04-07\",\n            \"expected_emi\": 54000,\n            \"default_emi_number\": 12,\n            \"settlement_amount\": 45000,\n            \"client_amount_recovered\": 0,\n            \"principal_outstanding_amount\": 45000,\n            \"expected_emi_interest_amount\": null,\n            \"expected_emi_principal_amount\": 45000,\n            \"other_penalty\": null\n        }\n    ],\n    \"co_applicant\": [\n        {\n            \"co_applicant_name\": \"Naveen Shekhawat\",\n            \"co_applicant_email\": \"pravinsingh@gmail.com\",\n            \"co_applicant_gender\": \"Male\",\n            \"co_applicant_contact_number\": \"9814274470\",\n            \"co_applicant_dob\": \"1990-06-29\",\n            \"co_applicant_address_text\": \"\",\n            \"co_applicant_state\": \"Rajasthan\",\n            \"co_applicant_city\": \"Alwar\",\n            \"co_applicant_pincode\": 301024\n        }\n    ],\n    \"references\": [\n        {\n            \"relation_with_applicant\": \"Colleague\",\n            \"name\": \"Abhishek Kumar\",\n            \"contact_number\": \"8802913432\"\n        }\n    ],\n    \"merchant_name\": \"Intellipaat\",\n    \"payment_link\": \"https://rzp.io/i/itKAy2q\"\n}"
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request POST 'https://api.credgenics.com/recovery/loan/{loan_id}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "client_customer_id": "189004",
    "loan_id": "283921",
    "loan_type": "Personal Loan",
    "applicant_name": "Shri Ram",
    "applicant_dob": "1992-03-23",
    "applicant_email": "shriram@gmail.com",
    "applicant_gender": "Male",
    "applicant_contact_number": "9805265926",
    "applicant_monthly_income": 40000,
    "applicant_cibil_score": 820,
    "applicant_occupation": "Job",
    "applicant_aadhar_number": "235498671293",
    "applicant_language": "hi",
    "applicant_pan_number": "ADJIY-3516-D",
    "total_loan_amount": 50000,
    "loan_tenure": 12,
    "client_loan_sanction_date": "2018-04-06",
    "loan_end_date": "2019-04-06",
    "interest_on_loan": 18,
    "tenure_finished": true,
    "security_type": "Secured immovable",
    "backed_by_surety": false,
    "loan_nbfc_name": "AKARA CAPITAL ADVISORS PVT. LTD.",
    "loan_nbfc_cin": "U65191TN1994PLC079235",
    "emi_amount": 6000,
    "product_type": "",
    "credit_account_number": "11271000005809",
    "credit_account_holder_name": "Sri Ram",
    "credit_bank_name": "HDFC Bank",
    "credit_account_holder_type": "Current",
    "credit_bank_ifsc_code": "HDFC0G45B4W",
    "document_details": [
        {
            "security_mode": "NACH",
            "document_number": "757493",
            "document_bank_name": "HDFC Bank",
            "document_bank_ifsc_code": "",
            "document_amount": 50000,
            "document_date": "2018-04-10",
            "document_dishonour_date": "2018-04-12",
            "document_signature_name": "",
            "document_bounce_bank_account_number": "",
            "document_bounce_bank_ifsc_code": "",
            "document_bounce_charges": null,
            "document_bounce_bank_name": "Yes Bank",
            "document_bounce_bank_address": "",
            "document_bounce_memo_date": null,
            "reason_of_document_bounce": ""
        }
    ],
    "business_name": "",
    "applicant_address": [
        {
            "applicant_address_type": "Home",
            "applicant_address_text": " 395/13 veer dua colony baldev nager",
            "applicant_state": "Rajasthan",
            "applicant_city": "Jodhpur",
            "applicant_pincode": 342001
        }
    ],
    "defaults": [
        {
            "total_claim_amount": 113000,
            "late_fee": 59443,
            "date_of_default": "2019-04-07",
            "expected_emi": 54000,
            "default_emi_number": 12,
            "settlement_amount": 45000,
            "client_amount_recovered": 0,
            "principal_outstanding_amount": 45000,
            "expected_emi_interest_amount": null,
            "expected_emi_principal_amount": 45000,
            "other_penalty": null
        }
    ],
    "co_applicant": [
        {
            "co_applicant_name": "Naveen Shekhawat",
            "co_applicant_email": "pravinsingh@gmail.com",
            "co_applicant_gender": "Male",
            "co_applicant_contact_number": "9814274470",
            "co_applicant_dob": "1990-06-29",
            "co_applicant_address_text": "",
            "co_applicant_state": "Rajasthan",
            "co_applicant_city": "Alwar",
            "co_applicant_pincode": 301024
        }
    ],
    "references": [
        {
            "relation_with_applicant": "Colleague",
            "name": "Abhishek Kumar",
            "contact_number": "8802913432"
        }
    ],
    "merchant_name": "Intellipaat",
    "payment_link": "https://rzp.io/i/itKAy2q"
}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"client_customer_id":"189004","loan_id":"283921","loan_type":"Personal Loan","applicant_name":"Shri Ram","applicant_dob":"1992-03-23","applicant_email":"shriram@gmail.com","applicant_gender":"Male","applicant_contact_number":"9805265926","applicant_monthly_income":40000,"applicant_cibil_score":820,"applicant_occupation":"Job","applicant_aadhar_number":"235498671293","applicant_language":"hi","applicant_pan_number":"ADJIY-3516-D","total_loan_amount":50000,"loan_tenure":12,"client_loan_sanction_date":"2018-04-06","loan_end_date":"2019-04-06","interest_on_loan":18,"tenure_finished":true,"security_type":"Secured immovable","backed_by_surety":false,"loan_nbfc_name":"AKARA CAPITAL ADVISORS PVT. LTD.","loan_nbfc_cin":"U65191TN1994PLC079235","emi_amount":6000,"product_type":"","credit_account_number":"11271000005809","credit_account_holder_name":"Sri Ram","credit_bank_name":"HDFC Bank","credit_account_holder_type":"Current","credit_bank_ifsc_code":"HDFC0G45B4W","document_details":[{"security_mode":"NACH","document_number":"757493","document_bank_name":"HDFC Bank","document_bank_ifsc_code":"","document_amount":50000,"document_date":"2018-04-10","document_dishonour_date":"2018-04-12","document_signature_name":"","document_bounce_bank_account_number":"","document_bounce_bank_ifsc_code":"","document_bounce_charges":null,"document_bounce_bank_name":"Yes Bank","document_bounce_bank_address":"","document_bounce_memo_date":null,"reason_of_document_bounce":""}],"business_name":"","applicant_address":[{"applicant_address_type":"Home","applicant_address_text":" 395/13 veer dua colony baldev nager","applicant_state":"Rajasthan","applicant_city":"Jodhpur","applicant_pincode":342001}],"defaults":[{"total_claim_amount":113000,"late_fee":59443,"date_of_default":"2019-04-07","expected_emi":54000,"default_emi_number":12,"settlement_amount":45000,"client_amount_recovered":0,"principal_outstanding_amount":45000,"expected_emi_interest_amount":null,"expected_emi_principal_amount":45000,"other_penalty":null}],"co_applicant":[{"co_applicant_name":"Naveen Shekhawat","co_applicant_email":"pravinsingh@gmail.com","co_applicant_gender":"Male","co_applicant_contact_number":"9814274470","co_applicant_dob":"1990-06-29","co_applicant_address_text":"","co_applicant_state":"Rajasthan","co_applicant_city":"Alwar","co_applicant_pincode":301024}],"references":[{"relation_with_applicant":"Colleague","name":"Abhishek Kumar","contact_number":"8802913432"}],"merchant_name":"Intellipaat","payment_link":"https://rzp.io/i/itKAy2q"});

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.credgenics.com/recovery/loan/{loan_id}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above command returns JSON structured like this:

```json
{
  "output": "Loan added successfully",
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to add new Loan / EMI to the data.

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->

### HTTP Request - POST

`POST https://api.credgenics.com/recovery/loan/{loan_id}`


### Path Parameters

| Parameter       | Description                         |
| --------------- | ----------------------------------- |
| loan_id         | Loan id of the loan                 |

### Request Headers

| Parameter | Description |
| --------- | ----------- |
| authenticationtoken | Auth token given by Credgenics |
| role | Role of the user |
| Content-Type | application/json |

<aside class="notice">
<code>client_customer_id</code> is required for this API. Other Request Body Parameters are same as that of Lending Add Loan API, so please refer to the Lending Add Loan API.
</aside>

### Response Status Code

<code>201 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.

<!-- CREDIT LINE - Update loan API------------------------- -->

## Update Loan API

```python
import requests

url = "https://api/credgenics.com/recovery/transaction/{client_customer_id}/{loan_id}"

payload = "{\n    \"total_loan_amount\": 60000\n}"
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}',
  'Content-Type': 'application/json'
}

response = requests.request("PATCH", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request PATCH 'https://api/credgenics.com/recovery/transaction/{client_customer_id}/{loan_id}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "total_loan_amount": 60000
}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"total_loan_amount":60000});

var requestOptions = {
  method: 'PATCH',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api/credgenics.com/recovery/transaction/{client_customer_id}/{loan_id}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above code returns JSON structured like this:

```json
{
  "output": "Transaction updated successfully",
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to update the details of any transaction of a customer.

### HTTP Request - PATCH

`PATCH https://api/credgenics.com/recovery/transaction/{client_customer_id}/{loan_id}`

### Path Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| client_customer_id        | The customer ID of the customer to update |
|loan_id|Transaction_id of the transaction to update |

### Request Headers

| Parameter | Description |
| --------- | ----------- |
| authenticationtoken | Auth token given by Credgenics |
| role | Role of the user |
| Content-Type | application/json |

### Response Status Code

<code>200 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.

<!-- CREDIT LINE - Update Payment API-------------------- -->

## Update Payment API

```python
import requests

url = "https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}"

payload = "{\n    \"client_customer_id\": \"189004\",\n    \"final_status\": \"Partially Recovered\",\n    \"amount_recovered\": 3450,\n    \"payment_method\": \"Online\",\n    \"date_of_default\": \"2020-01-23\"\n}"
headers = {
  'authenticationtoken': '{auth_token}',
  'role': '{role}',
  'Content-Type': 'application/json'
}

response = requests.request("PATCH", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```

```shell
curl --location --request PATCH 'https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}' \
--header 'authenticationtoken: {auth_token}' \
--header 'role: {role}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "client_customer_id": "189004",
    "final_status": "Partially Recovered",
    "amount_recovered": 3450,
    "payment_method": "Online",
    "date_of_default": "2020-01-23"
}'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("authenticationtoken", "{auth_token}");
myHeaders.append("role", "{role}");
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({"client_customer_id":"189004","final_status":"Partially Recovered","amount_recovered":3450,"payment_method":"Online","date_of_default":"2020-01-23"});

var requestOptions = {
  method: 'PATCH',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above code returns JSON structured like this:

```json
{
  "output": "Data updated successfully",
  "message": "success",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

Use this API to update the payment details of a customer.

### HTTP Requests - PATCH

`GET https://api.credgenics.com/recovery/recovery/update/{loan_id}?allocation_month={allocation_month}`

### Path Parameters

| Parameter | Description |
| ------ | ------ |
| loan_id | Loan id of the recovered loan |
| allocation_month | Allocation month of the recovered loan. Eg - "2021-2-01" |

<aside class="notice">
NOTE: Date will always be '01' and month should always be without leading '0' in <code>allocation_month</code> key
</aside>

### Request Headers

| Parameter | Description |
| ------ | ------ |
| authenticationtoken | The authentication token assigned to you by Credgenics |
| role | The role of the user |
| Content-Type | "application/json" |

### Request Body Parameters

| Key Name | Type | Required |Description |
| ------ | ------ | ------ | ------ |
| client_customer_id | string | True | Client customer id of the customer. |
| final_status | string | True | The status of the loan. Choices - Partially Recovered, Closed |
| recovery_method | string | False | Recovery method of the loan. Choices - Communications, Field Collection, Legal |
| payment_method | string | True | Method by which the payment has been made. Choices - Cash, Online, Cheque, Application, Bank Account Transfer, Payment Link. |
| date_of_default | date | True  | Date of default of the loan ( Required only if final_status is Partially Recovered ) |
| closure_with | string | False | Choices for closure - NOC, Settlement |
| payment_reference_number | string | False | Payment Reference Number |
| payment_mode | string | False | Mode of payment |

<aside class="notice">
<code>client_customer_id</code> is required for this API.
</aside>

### Response Status Code

<code>200 OK</code> for a successful request.

<code>401 Unauthorized</code> if authentication failed. API credentials are incorrect.

<code>400 Bad Request</code> if the request payload had some error. Specific error is provided in the response.