# NSF Score

## Overview

The NSF Score model is designed to evaluate the likelihood of a business or individual being unable to pay their debts on time. It is used to determine the likelihood of a loan being repaid on time.

## How to Use

### Example Request

```bash
curl -X POST "https://your-api-url/v1/score" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json" \
-F "model=nsfscore"
```

### Example Response


```json
{
  "model": {
    "adverse_action_items": [
      {
        "AA_Description": "Average amount of salary advance payments in last 1 month",
        "AA_code": "AA4"
      },
      {
        "AA Description": "Maximum amount of debt payments made in last 1 month",
        "AA Code": "AA32"
      },
      {
        "AA_Description": "Number of ecommerce payments made over $5 in last 1 month",
        "AA_code": "AA25"
      }
      {
        "AA_Description": "Number of days the daily overall balance in cash/checking/saving accounts was less than $1000 in last 1 month",
        "AA_code": "AA17"
      },
    ],
    "model_name": "nsfscore",
    "pred_prob": 0.21633579640379053,
    "score": 652.0
  }
}
```

