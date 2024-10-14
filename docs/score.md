# Score

## Overview
The `/v1/score` endpoint calculates a score based on the input data. This scoring mechanism is often used in risk assessment or predictive modeling scenarios to evaluate the likelihood of specific outcomes.

### Example Request
- Python
```python
import requests
import json

url = "https://your-api-url/v1/score"
headers = {
    "x-api-key": "your_api_key",
    "x-client-id": "your_client_id"
}
data = {
    "file": "@path/to/yourjson/file.json",
    "model": "model_name"
}

response = requests.post(url, headers=headers, data=json.dumps(data))

print(response.json())
```
- Curl
```bash
curl -X POST "https://your-api-url/v1/score" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path/to/your/json/file.json" \
-F "model=model_name"
```

### Example Response
```json
{
  "metadata": {
    "coverage 1 month": true,
    "coverage 3 months": true,
    "coverage 6 months": true,
    "message": "Success - score generated",
    "product": "Fincepta Cashflow Data Enrichment"
  },
  "model": {
    "adverse_action_items": [
      {
        "AA_Description": "Average amount of salary advance payments in last 1 month",
        "AA_code": "AA4"
      },
      {
        "AA_Description": "Number of days the daily overall balance in cash/checking/saving accounts was less than $1000 in last 1 month",
        "AA_code": "AA17"
      },
      {
        "AA_Description": "Number of salary advance payments made below $100 in last 6 months",
        "AA_code": "AA34"
      },
      {
        "AA_Description": "Number of ecommerce payments made over $5 in last 1 month",
        "AA_code": "AA25"
      }
    ],
    "model_code": "cash50",
    "model_name": "CashAdvance50USD",
    "pred_prob": 0.1163879930973053,
    "score": 696.0
  }
}
```