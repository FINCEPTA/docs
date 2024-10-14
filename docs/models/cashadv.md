# Cash Advance

## Overview

The Cash Advance model is designed to evaluate the creditworthiness of an individual or business based on their financial history and credit score. It is used to determine the likelihood of a loan being repaid on time.

## How to Use

### Example Request

```bash
curl -X POST "https://your-api-url/v1/score" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
-F "model="cashadvance"
```

### Example Response

```json
{
    "pred_prob": 0.1163879930973053,
    "score": 696.0
}
```
