
# **Enrich**

## Overview
The `/v1/enrich` endpoint enriches transaction data by adding contextual information. This can enhance the value of your dataset by providing additional attributes that can improve analysis and modeling.

## How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - Data can be sent as a JSON file or as JSON data in the request body.
  - The file should be in `.json` format if uploading, and the parameter should be `file`.
  - If sending data in the request body, make sure it is in JSON format.

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
    "file": "@path/to/yourjson/file.json"
}

response = requests.post(url, headers=headers, data=json.dumps(data))

print(response.json())
```
- Curl
```bash
curl -X POST "https://your-api-url/v1/enrich" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path/to/your/json/file.json"
```




### Example Response

<div style="overflow-x: auto; max-width: 100%; max-height: 500px; overflow-y: auto;">
<pre><code>
```json
{
  "enriched_transactions": [
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 30.0,
      "iso_currency_code": "USD",
      "name": "Publix",
      "pending": false,
      "transaction_category_code": "food_debit",
      "transaction_category_num": 53,
      "transaction_id": "ydM441pwoBFyZOVEmjLBcqja5ANbPwFRYjg8L",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 22.78,
      "iso_currency_code": "USD",
      "name": "Shell",
      "pending": false,
      "transaction_category_code": "gasstation_debit",
      "transaction_category_num": 78,
      "transaction_id": "MM4BBgRNwdHRNmVqXQ4RIgVYQ9MajKC0gZYyn",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 4.99,
      "iso_currency_code": "USD",
      "name": "Oneblinc Salary Adv",
      "pending": false,
      "transaction_category_code": "ewapmnt_debit",
      "transaction_category_num": 6,
      "transaction_id": "KVjPPgNp5RU3Vk1XB5NLTAyDOxk7weIyJxmbd",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 25.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "avEdd6R4XxCkVKd4Re3qSEre416jabT9OVjv1",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": -150.0,
      "iso_currency_code": "USD",
      "name": "ATM Deposit",
      "pending": false,
      "transaction_category_code": "atm_credit",
      "transaction_category_num": 1,
      "transaction_id": "k5Eyykp70VC835J7egM6iPDnwN4yoVHb1VvYR",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 25.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "mbEkkvpVrMH5KmEVQrNdFJPO6JJDwMFNVomxZ",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 22.16,
      "iso_currency_code": "USD",
      "name": "Ole Times Lak",
      "pending": false,
      "transaction_category_code": "other_debit",
      "transaction_category_num": 128,
      "transaction_id": "RpZAAgRLP1HoVa0L6A9pHMa8jL7dpki4gBBYr",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 12.24,
      "iso_currency_code": "USD",
      "name": "Ole Times Lak",
      "pending": false,
      "transaction_category_code": "other_debit",
      "transaction_category_num": 128,
      "transaction_id": "Qn8kkgR61DfpK4D6Q5VvsYvRa61dpmhzPdd60",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 10.0,
      "iso_currency_code": "USD",
      "name": "Hard Rock",
      "pending": false,
      "transaction_category_code": "entertainment_debit",
      "transaction_category_num": 71,
      "transaction_id": "E5yddjROA7C4MPqpeBR6FQRYXe1zg8tJNLLzk",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 5.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "ngnAA0pOxECEka3OJ5jMHEomdapDXvH0Vaaod",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 28.09,
      "iso_currency_code": "USD",
      "name": "Red Ginger",
      "pending": false,
      "transaction_category_code": "other_debit",
      "transaction_category_num": 128,
      "transaction_id": "p9MxxrpEYQiwv0zPgVnMF8P4nLbrExfZm66bE",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 24.91,
      "iso_currency_code": "USD",
      "name": "Zaxbys",
      "pending": false,
      "transaction_category_code": "food_debit",
      "transaction_category_num": 53,
      "transaction_id": "vQMgg6pN51SqxY45wDdmC57vn9xgVmFkMRgRk",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 17.1,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "DZ3xx0RVvgFX31o07DRptY47n0oD9NFRpQVRz",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 16.09,
      "iso_currency_code": "USD",
      "name": "Sakura Buffet",
      "pending": false,
      "transaction_category_code": "other_debit",
      "transaction_category_num": 128,
      "transaction_id": "0L0nnjOm5qUDxVbZynaJHBj61aPwBNCv5naBx",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 14.3,
      "iso_currency_code": "USD",
      "name": "Lake City Nutrit Nutrition",
      "pending": false,
      "transaction_category_code": "food_debit",
      "transaction_category_num": 53,
      "transaction_id": "1DjnnrJKNBHRNVgze1krFM8V5VrLDaUjd9kRg",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 14.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "wnMRRLpe9PfBeEPmJ8wRhZa3R0jdg6UvqJyvR",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 10.5,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "qVMrr4pRYdU60qNwmKkOfaj4oVkyqEcEo5BEP",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 8.53,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "KVjPPgNp5RU3Vk1XB5NYhV0g4xoRbPfm5K1mJ",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 6.57,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "zwMaaPd6j3HK5X7poqDgFedr9r7Vo6fdXPEN6",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": -100.0,
      "iso_currency_code": "USD",
      "name": "Internal Account Transfer",
      "pending": false,
      "transaction_category_code": "banktrnsfr_credit",
      "transaction_category_num": 116,
      "transaction_id": "mbEkkvpVrMH5KmEVQrN1I5Y9d9XwJPF3w7pqA",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 5.25,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "drpLL1aJ4ZfE6vPJ1YmnFqQRNRMxzwtym5ZE9",
      "unofficial_currency_code": null
    },
    {
      "account_id": "Qn8kkgR61DfpK4D6Q5zMURPnNKY1PnUzZknyv",
      "amount": 100.0,
      "iso_currency_code": "USD",
      "name": "Internal Account Transfer",
      "pending": false,
      "transaction_category_code": "banktrnsfr_debit",
      "transaction_category_num": 117,
      "transaction_id": "Qn8kkgR61DfpK4D6Q5VATx9eLebdorIzBa7Zx",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 221.81,
      "iso_currency_code": "USD",
      "name": "Advance America",
      "pending": false,
      "transaction_category_code": "loanpmnt_debit",
      "transaction_category_num": 44,
      "transaction_id": "63JeewDjNAHwRvdN4ak9i0qkoNpzbjfNkZyNN",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 150.0,
      "iso_currency_code": "USD",
      "name": "Wes Student Tic Httpswes",
      "pending": false,
      "transaction_category_code": "education_debit",
      "transaction_category_num": 103,
      "transaction_id": "drpLL1aJ4ZfE6vPJ1YmZS1z8kEXZaAHQVPyQK",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 62.82,
      "iso_currency_code": "USD",
      "name": "Enova Loc Netcrcoll",
      "pending": false,
      "transaction_category_code": "loanpmnt_debit",
      "transaction_category_num": 44,
      "transaction_id": "LOrqqMRXdQHjPAegO7XNt6R9aZx7JdFBDjmBm",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 47.01,
      "iso_currency_code": "USD",
      "name": "Sunstop St",
      "pending": false,
      "transaction_category_code": "other_debit",
      "transaction_category_num": 128,
      "transaction_id": "AxP88k0gB5FDVoy0MeO1uNBP90VbkQUnJxbnY",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 31.5,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "BJqxxAj7EoUEDnA45aejSjYq6an0Z9f7aRd7L",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 27.66,
      "iso_currency_code": "USD",
      "name": "Klarna",
      "pending": false,
      "transaction_category_code": "bnplpmnt_debit",
      "transaction_category_num": 42,
      "transaction_id": "63JeewDjNAHwRvdN4akLtQXgZgmAqaIyBO7va",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 24.88,
      "iso_currency_code": "USD",
      "name": "Klarna",
      "pending": false,
      "transaction_category_code": "bnplpmnt_debit",
      "transaction_category_num": 42,
      "transaction_id": "mbEkkvpVrMH5KmEVQrN9cQJ18qNjEmtvJE3vM",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 23.13,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "ydM441pwoBFyZOVEmjLqsLmeRA08dzFg7P3g7",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 22.58,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "vQMgg6pN51SqxY45wDdyuBKQvbwgxat0DPk0n",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 21.04,
      "iso_currency_code": "USD",
      "name": "Klarna",
      "pending": false,
      "transaction_category_code": "bnplpmnt_debit",
      "transaction_category_num": 42,
      "transaction_id": "LOrqqMRXdQHjPAegO7XBc4NMqMvnRwUm6VzAZ",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 19.59,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "DZ3xx0RVvgFX31o07DRdc1aMQMBk45hV7mknX",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 10.29,
      "iso_currency_code": "USD",
      "name": "Sunstop St",
      "pending": false,
      "transaction_category_code": "other_debit",
      "transaction_category_num": 128,
      "transaction_id": "9k5xxDqazjfoAVb83OXxTv10YmOgpjFk05o6r",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 1.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "0L0nnjOm5qUDxVbZynavU0zJ13nD3NfvXbRoN",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 389.42,
      "iso_currency_code": "USD",
      "name": "Progressive",
      "pending": false,
      "transaction_category_code": "insurance_debit",
      "transaction_category_num": 97,
      "transaction_id": "jZE33Kpg09FJex5Y1Mn9sx7aJONqOnfjBLamL",
      "unofficial_currency_code": null
    },
    {
      "account_id": "ngnAA0pOxECEka3OJ59nFm8bg7Ep8bI0d8yQo",
      "amount": -25.0,
      "iso_currency_code": "USD",
      "name": "Defense Finance and Accounting Service",
      "pending": false,
      "transaction_category_code": "othservices_credit",
      "transaction_category_num": 104,
      "transaction_id": "ngnAA0pOxECEka3OJ5jefxA8LXQ06JtMgxOQ6",
      "unofficial_currency_code": null
    },
    {
      "account_id": "Qn8kkgR61DfpK4D6Q5zMURPnNKY1PnUzZknyv",
      "amount": -25.0,
      "iso_currency_code": "USD",
      "name": "Defense Finance and Accounting Service",
      "pending": false,
      "transaction_category_code": "othservices_credit",
      "transaction_category_num": 104,
      "transaction_id": "p9MxxrpEYQiwv0zPgVneIXJAYEyKaOU7gdPej",
      "unofficial_currency_code": null
    },
    {
      "account_id": "p9MxxrpEYQiwv0zPgVXrC4AzRQ8bAzUZBOVeM",
      "amount": -60.0,
      "iso_currency_code": "USD",
      "name": "Defense Finance and Accounting Service",
      "pending": false,
      "transaction_category_code": "payroll_credit",
      "transaction_category_num": 125,
      "transaction_id": "X1EXXga30KHLe6r3qAdbfYaNxZ80wqFO5VvrM",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 50.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "ydM441pwoBFyZOVEmjL7TL4OD339jKUrbMMdz",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 6.0,
      "iso_currency_code": "USD",
      "name": "McDonalds",
      "pending": false,
      "transaction_category_code": "food_debit",
      "transaction_category_num": 53,
      "transaction_id": "3P4nnawAvyFwZK9dRBkvhz5DjQQqvkCVExx4N",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": -1340.17,
      "iso_currency_code": "USD",
      "name": "Defense Finance and Accounting Service",
      "pending": false,
      "transaction_category_code": "payroll_credit",
      "transaction_category_num": 125,
      "transaction_id": "LOrqqMRXdQHjPAegO7XYhdBK1pxew6Id3Lkoz",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": -69.0,
      "iso_currency_code": "USD",
      "name": "Internal Account Transfer",
      "pending": false,
      "transaction_category_code": "banktrnsfr_credit",
      "transaction_category_num": 116,
      "transaction_id": "RpZAAgRLP1HoVa0L6A9dcZz7zQ5PgZt4Eop56",
      "unofficial_currency_code": null
    },
    {
      "account_id": "p9MxxrpEYQiwv0zPgVXrC4AzRQ8bAzUZBOVeM",
      "amount": 69.0,
      "iso_currency_code": "USD",
      "name": "Internal Account Transfer",
      "pending": false,
      "transaction_category_code": "banktrnsfr_debit",
      "transaction_category_num": 117,
      "transaction_id": "ngnAA0pOxECEka3OJ5jDc81p1QLxw8F0PNY6x",
      "unofficial_currency_code": null
    },
    {
      "account_id": "p9MxxrpEYQiwv0zPgVXrC4AzRQ8bAzUZBOVeM",
      "amount": 50.0,
      "iso_currency_code": "USD",
      "name": "Internal Account Transfer",
      "pending": false,
      "transaction_category_code": "banktrnsfr_debit",
      "transaction_category_num": 117,
      "transaction_id": "e4pDDPa8v5HRLna8OjpYiOzdoRRvpMUMZ77rN",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 25.0,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "ORxyyEXdL6CD3jKd7mX4FbvzRN9Pg3FV69w05",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 10.12,
      "iso_currency_code": "USD",
      "name": "Shell",
      "pending": false,
      "transaction_category_code": "gasstation_debit",
      "transaction_category_num": 78,
      "transaction_id": "ngnAA0pOxECEka3OJ5jpiYdK07V3dxS5wZVD7",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": -0.01,
      "iso_currency_code": "USD",
      "name": "ATM Deposit",
      "pending": false,
      "transaction_category_code": "atm_credit",
      "transaction_category_num": 1,
      "transaction_id": "RpZAAgRLP1HoVa0L6A9gi0jJ4NEojPCbj7gNK",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": -50.0,
      "iso_currency_code": "USD",
      "name": "Internal Account Transfer",
      "pending": false,
      "transaction_category_code": "banktrnsfr_credit",
      "transaction_category_num": 116,
      "transaction_id": "KVjPPgNp5RU3Vk1XB5NJsV3mrnnXy5fnqXX8k",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 10.5,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "wnMRRLpe9PfBeEPmJ8w6i5ZakzQmNZceJK4eV",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 5.25,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "PQJKKgRwDLSgyrzwxBm4ivxpQ46PXxFa5oxaq",
      "unofficial_currency_code": null
    },
    {
      "account_id": "MM4BBgRNwdHRNmVqXQZAtoKOBRZrKOF5jQ1da",
      "amount": 2.7,
      "iso_currency_code": "USD",
      "name": "Cash App",
      "pending": false,
      "transaction_category_code": "p2ptrfr_debit",
      "transaction_category_num": 18,
      "transaction_id": "p9MxxrpEYQiwv0zPgVnRS5O0gNePzOc7L307g",
      "unofficial_currency_code": null
    }
  ]
}
```
</pre>
</div>