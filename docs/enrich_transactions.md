
# **Enrich Transactions**

## Overview
The `/v1/enrich_transaction` endpoint enriches transaction data by categorizing the transactions into our custom categories.


## How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - Data can be sent as a JSON file or as JSON data in the request body.
  - The file should be in `.json` format if uploading, and the parameter should be `file`.
  - If sending data in the request body, make sure it is in JSON format.

### Sample Input Data

```json
{
    "transactions": [
        {   "transaction_id": "transaction_id",
            "description": "description",
            "amount": 0.0,
            "date": "2021-04-01",
            "iso_currency_code": "iso_currency_code",
        },
        {   "transaction_id": "transaction_id",
            "description": "description",
            "amount": 0.0,
            "date": "2021-04-01",
            "iso_currency_code": "iso_currency_code",
        }
        
    ]
}
```
***NOTE***
- JSON input with key `transactions` and value is a `list` of `dictionary` of transactions,
- Required fields in the dictionary of each transaction are `transaction_id`, `description`, `amount`, `date`, `iso_currency_code`
- This endpoint supports both JSON data and JSON files as input.


### Example Request

- Python
```python
import requests
import json

url = "https://your-api-url/v1/enrich"
headers = {
    "x-api-key": "your_api_key",
    "x-client-id": "your_client_id"
}
data = {
    "transactions": [
        {   "transaction_id": "transaction_id",
            "description": "description",
            "amount": 0.0,
            "date": "2021-04-01",
            "iso_currency_code": "iso_currency_code",
        },
        {   "transaction_id": "transaction_id",
            "description": "description",
            "amount": 0.0,
            "date": "2021-04-01",
            "iso_currency_code": "iso_currency_code",
        }
        
    ]
}

response = requests.post(url, headers=headers, data=json.dumps(data))

print(response.json())
```
- Curl
```bash
curl -X POST "https://your-api-url/v1/enrich" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-d "{
    "transactions": [
        {   "transaction_id": "transaction_id",
            "description": "description",
            "amount": 0.0,
            "date": "2021-04-01",
            "iso_currency_code": "iso_currency_code",
        },
        {   "transaction_id": "transaction_id",
            "description": "description",
            "amount": 0.0,
            "date": "2021-04-01",
            "iso_currency_code": "iso_currency_code",
        }
        
    ]
}"
```

### Example Response

<div style="overflow-x: auto; max-width: 100%; max-height: 400px; overflow-y: auto;">
<pre><code>
```json
{
  'enriched_transactions':
  [
  {'account_id': '10bfb591-da0b-48d1-a647-c8d3e5eb7cc6',
   'amount': -250.0,
   'date': '2021-07-22',
   'description': 'Online Transfer from SAV ...6830 transaction#: 12229037507',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'banktrnsfr_credit',
   'transaction_category_num': 116,
   'transaction_id': '182c43e0-8d10-4d51-938b-67d9f257b212'},
  {'account_id': '01e357b1-e621-42b4-a47e-4ba2c4fae64b',
   'amount': 70.0,
   'date': '2021-02-03',
   'description': 'VENMO            PAYMENT    5205841049      WEB ID: 3264681992',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'p2ptrfr_debit',
   'transaction_category_num': 18,
   'transaction_id': 'ff9989f5-83db-444c-9ca8-3ab51ee496da'},
  {'account_id': '58790645-dc1e-4947-847a-d4369e245324',
   'amount': 10.56,
   'date': '2020-12-28',
   'description': 'TARGET DEBIT CRD ACH TRAN   000681481903991 WEB ID: 1410215170',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'groceries_debit',
   'transaction_category_num': 65,
   'transaction_id': '632f96af-816e-4409-bd96-fb651fe52210'},
  {'account_id': '883585c9-8069-429c-a3d3-0cc40fd1f56e',
   'amount': 30.0,
   'date': '2021-01-19',
   'description': 'VENMO            PAYMENT    5107205503      WEB ID: 3264681992',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'p2ptrfr_debit',
   'transaction_category_num': 18,
   'transaction_id': '9719fb97-0dc9-4167-b558-4ca88bb49836'},
  {'account_id': 'b9d35a2a-4762-4831-8a8a-3a147c34f344',
   'amount': 85.63,
   'date': '2021-03-10',
   'description': 'TARGET DEBIT CRD ACH TRAN   000681481901399 POS ID: 1410215170',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'groceries_debit',
   'transaction_category_num': 65,
   'transaction_id': '44649b83-45df-4d0e-bf18-44f96ece3367'},
  {'account_id': '7b779271-8fdd-435a-962a-d7ef423b4f01',
   'amount': 33.59,
   'date': '2021-08-11',
   'description': 'AFFIRM *PAYMENT 855-423-3729 CA              08/10',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'bnplpmnt_debit',
   'transaction_category_num': 42,
   'transaction_id': 'd2152a8f-de3b-448e-8034-e7d167b46d1a'},
  {'account_id': 'b7765b2a-b407-4155-b644-289f8d2460e5',
   'amount': 400.0,
   'date': '2020-02-24',
   'description': 'Payment to Chase card ending in 9617 02/24',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'banktrnsfr_debit',
   'transaction_category_num': 117,
   'transaction_id': '554933aa-a46d-4bcd-8a1a-db614ccde300'},
  {'account_id': 'f71661d6-9896-4c77-b429-f4d0db05a2ee',
   'amount': 250.0,
   'date': '2021-06-25',
   'description': 'Online Transfer to  SAV ...4260 transaction#: 11956760410',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'banktrnsfr_debit',
   'transaction_category_num': 117,
   'transaction_id': '06182999-8149-4757-bc3c-22817905db3e'},
  {'account_id': 'eecdf14e-5e31-4fef-8976-50709c1b9d83',
   'amount': 300.0,
   'date': '2021-07-01',
   'description': 'VENMO            PAYMENT    1014465676779   WEB ID: 3264681992',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'p2ptrfr_debit',
   'transaction_category_num': 18,
   'transaction_id': '6665c42c-fa76-496f-b4c7-bd0dee3fca83'},
  {'account_id': '051d7f8f-2b95-426f-b5fd-2cc21732f82d',
   'amount': 25.0,
   'date': '2021-09-20',
   'description': 'STARBUCKS 800-782-728 800-782-7282 WA        09/17',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'food_debit',
   'transaction_category_num': 53,
   'transaction_id': 'fd2671b9-a06f-4279-9523-1c3ef45cf8e0'},
  {'account_id': 'f3d6466f-a36a-40a4-87ba-e2ee474a1893',
   'amount': 2.34,
   'date': '2021-03-15',
   'description': 'TARGET DEBIT CRD ACH TRAN   000681481903991 WEB ID: 1410215170',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'groceries_debit',
   'transaction_category_num': 65,
   'transaction_id': '52c31c4c-0f4d-4b7b-a238-7ff401a15346'},
  {'account_id': 'e61b6dec-b793-4813-8213-ec3541f48f0c',
   'amount': -39.72,
   'date': '2020-11-13',
   'description': 'VENMO            CASHOUT                    PPD ID: 5264681992',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'p2ptrfr_credit',
   'transaction_category_num': 17,
   'transaction_id': 'aa754f05-9a72-4dda-b6ce-eb6ae0cc790e'},
  {'account_id': '716cc7ab-c1c6-4ed9-8e19-91199b767023',
   'amount': 500.0,
   'date': '2019-10-15',
   'description': 'Payment to Chase card ending in 9617 10/15',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'banktrnsfr_debit',
   'transaction_category_num': 117,
   'transaction_id': 'f09b570f-b821-4ecf-a9fb-c320a65298f1'},
  {'account_id': '41f52e49-ee8d-4014-b7d5-b8e145a328af',
   'amount': 18.83,
   'date': '2021-06-14',
   'description': 'TARGET DEBIT CRD ACH TRAN   000681481903991 WEB ID: 1410215170',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'groceries_debit',
   'transaction_category_num': 65,
   'transaction_id': '0251b871-cefa-47c9-bf93-62ec317c9db2'},
  {'account_id': 'e5e61aab-f39a-4ab1-b8fc-b7aacb8d3f0c',
   'amount': 1000.0,
   'date': '2021-02-25',
   'description': 'Online Transfer to SAV ...4260 transaction#: 11253495056 02/25',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'banktrnsfr_debit',
   'transaction_category_num': 117,
   'transaction_id': 'b05db037-9fe5-4f67-9b25-739922e1090d'},
  {'account_id': '8d477ff8-aae0-4262-ac21-88f2e6fa95f9',
   'amount': 58.0,
   'date': '2021-08-16',
   'description': 'VENMO            PAYMENT    1015216990266   WEB ID: 3264681992',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'p2ptrfr_debit',
   'transaction_category_num': 18,
   'transaction_id': '639ce8fb-25b7-4a41-869c-646c25ca916b'},
  {'account_id': '6de3259e-bee4-4062-929a-3d01a84e6bf3',
   'amount': -600.0,
   'date': '2021-02-02',
   'description': 'VENMO            CASHOUT                    PPD ID: 5264681992',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'p2ptrfr_credit',
   'transaction_category_num': 17,
   'transaction_id': '04b324ae-4a7b-4117-9293-d98d942bb565'},
  {'account_id': '31b12334-f5cf-4ea8-ac5d-3782bbdd47c9',
   'amount': 6.06,
   'date': '2021-08-05',
   'description': 'TARGET DEBIT CRD ACH TRAN   000681481903991 WEB ID: 1410215170',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'groceries_debit',
   'transaction_category_num': 65,
   'transaction_id': '51087e76-53e4-4fb8-b0fd-71397f112695'},
  {'account_id': '04d41e3e-7a43-4a5c-9fe0-3be6e51365b7',
   'amount': 100.0,
   'date': '2021-09-13',
   'description': 'Payment to Chase card ending in 9617 09/13',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'banktrnsfr_debit',
   'transaction_category_num': 117,
   'transaction_id': '7e2b3a4d-2ca7-4420-9e85-5845e9568a25'},
  {'account_id': '175f0df3-b792-49fb-9ae2-6485c691318d',
   'amount': -500.0,
   'date': '2020-09-03',
   'description': 'FEMA TREAS 310     MISC PAY 627445996700700 CCD ID: 9101036151',
   'iso_currency_code': 'USD',
   'transaction_category_code': 'taxrefund_credit',
   'transaction_category_num': 7,
   'transaction_id': 'ab49cc2a-b8ce-45a7-992c-5071620268ad'}
  ]
}
```
</pre>
</div>