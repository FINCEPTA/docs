
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
    {
        "account_id": "EvDQbyQKDeSAw1nkzer7S69y5qLAD6tdvxpDz",
        "amount": -40.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "Transfer from DDA Acct No. @XXXXXXXXXX@5439",
        "pending": false,
        "recurrence": true,
        "recurrence_frequency": "semimonthly",
        "transaction_category_code": "banktrnsfr_credit",
        "transaction_id": "54Vg3mgQVbhY5bXAM3aJTDAjwKQpE5U4ywVK4"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 148.04,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "ACH Debit 0430368139 SPIRE FTWEB72885346 FIRSTECH ALAN R JENNINGS TEL 071104712310493",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "banktrnsfr_debit",
        "transaction_id": "pLOwnZON1NSPeJj4XPMBhmB0neOVL6u416rPO"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 148.04,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "0430368139 SPIRE FTWEB72885346 FIRSTECH ALAN R JENNINGS TEL 071104712310493",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "other_debit",
        "transaction_id": "P10qbJq80eFRkKNbDxEOHxn3jK77q9FAgoJVn"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 40.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "Transfer to Savings Transfer to Savings Acct No. 6500559",
        "pending": false,
        "recurrence": true,
        "recurrence_frequency": "semimonthly",
        "transaction_category_code": "banktrnsfr_debit",
        "transaction_id": "QoMYKeMdjdi6J31Oz6vAcwqoa9QO6VH4DdR3p"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 40.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "Transfer to Savings Acct No. @XXXXXXXXXX@0559",
        "pending": false,
        "recurrence": true,
        "recurrence_frequency": "semimonthly",
        "transaction_category_code": "banktrnsfr_debit",
        "transaction_id": "DALDY3DyLetKdQ9nm7BpiYO6EB55JzuRMwgPv"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 40.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "Check-Inclearing #1605",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "check_debit",
        "transaction_id": "RoMYkeMwrwiL3j74RLpvCOBxjD6eLVTqQBPJX"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 40.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "Check-Inclearing 1605 1605",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "check_debit",
        "transaction_id": "LwKnJrn4KehqBY8aQOxNi6Er3vwwKXfBNZ8pE"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 35.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS Pre-Authorized Debit - DDA DBT CRD 1753 08/15/23 DJKI22AV NRA MEMBERSHIP INTERNE VA C#7461",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "debcardpurchase_debit",
        "transaction_id": "YQbYadbB5BfyxmpNnyOVtRej0goJDVCqxdjAz"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 35.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "DBT CRD 1753 08/15/23 DJKI22AV NRA MEMBERSHIP INTERNE VA C#7461",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "debcardpurchase_debit",
        "transaction_id": "yPvV6MVZvYi9roz4QmYquLYxyVwwKnIgrpamV"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 32.45,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS Debit - DDA POS DEB 1654 08/14/23 00012064 CASEYS #2348 CASEYS 2348 FREDERICKTOWN MO C#7461",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "groceries_debit",
        "transaction_id": "X5bY4ebqZqF3b1X7Y3JQIoJ4jyqdLecawXQvr"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 32.45,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS DEB 1654 08/14/23 00012064 CASEYS #2348 CASEYS 2348 FREDERICKTOWN MO C#7461",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "groceries_debit",
        "transaction_id": "qJP9xM90P5uj37rZzmVOsaYO6nNNzesEqDnQe"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 14.16,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS Debit - DDA POS DEB 2136 08/14/23 00532124 SOUTHBOUND FUEL 18200 HWY 32 SAINTE GENEVI MO C#7461",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "gasstation_debit",
        "transaction_id": "No1OBY15A5iYP5MnzYKyCZgxEdeoVyCLJdnNR"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 14.16,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS DEB 2136 08/14/23 00532124 SOUTHBOUND FUEL 18200 HWY 32 SAINTE GENEVI MO C#7461",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "gasstation_debit",
        "transaction_id": "BKw0Vq0Bwehkd0X6V5rjhjogAePPLVH7g3N1P"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 11.99,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS Recurring Debit DBT CRD 0402 08/15/23 DJW17OYU ROKU FOR CBS INTERACTI 8162728107 DE C#5066",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "entertainment_debit",
        "transaction_id": "nwZYQJZKLKFOe6KB9OMPURP4dyJOaqCpna6OY"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 11.99,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "DBT CRD 0402 08/15/23 DJW17OYU ROKU FOR CBS INTERACTI 8162728107 DE C#5066",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "entertainment_debit",
        "transaction_id": "1vbx1jxOb8SYr0OjvepATb3JgraaZ1Ug0nAwr"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": 3.7,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS Debit - DDA POS DEB 0924 08/15/23 10786293 BMW 2 FREDERICK BMW 2 FREDERICK FREDERICKTOWN MO C#5066",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "debcardpurchase_debit",
        "transaction_id": "ezBYQkB6n6h8e3odm8k9tz8y7QOnqvfbJ7oyn"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": 3.7,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "POS DEB 0924 08/15/23 10786293 BMW 2 FREDERICK BMW 2 FREDERICK FREDERICKTOWN MO C#5066",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "debcardpurchase_debit",
        "transaction_id": "3m7zq4zE75tYg4X37RpxTz8E9BJJkwUAVoLan"
    },
    {
        "account_id": "pLOwnZON1NSPeJj4XPMBhmrojKzDgxF4ORjeY",
        "amount": -1564.2,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "ACH Credit 1204895317 Gentry Inc. 021000026641877 PPD Alan R Jennings Jr. Bill.com",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "payroll_credit",
        "transaction_id": "zAZKQYZN0NfpyrPanpMgfLaojd4xXDInZJYpn"
    },
    {
        "account_id": "M6kjJ4jakeiJ3Oe1KXPpFwmxJYEqOwC0qoMYb",
        "amount": -1564.2,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "1204895317 Gentry Inc. 021000026641877 PPD Alan R Jennings Jr. Bill.com",
        "pending": false,
        "recurrence": false,
        "recurrence_frequency": null,
        "transaction_category_code": "othservices_credit",
        "transaction_id": "KdyKmjKryeSvnE84aBOYUVLdB6ee5ZHmnENrP"
    },
    {
        "account_id": "X5bY4ebqZqF3b1X7Y3JQIorz70D5pVsa798rn",
        "amount": -40.0,
        "date": "2023-08-15",
        "iso_currency_code": "USD",
        "name": "Transfer from DDA Transfer from DDA Acct No. 2995439",
        "pending": false,
        "recurrence": true,
        "recurrence_frequency": "semimonthly",
        "transaction_category_code": "banktrnsfr_credit",
        "transaction_id": "ykAyQYANvNFEopPNeEMrC4eLnVkNPwtg1MxV6"
    }
  ]
}
```
</pre>
</div>