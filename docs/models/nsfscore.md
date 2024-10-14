# NSF Score

## Overview

The NSF Score model is designed to evaluate the likelihood of a business or individual being unable to pay their debts on time. It is used to determine the likelihood of a loan being repaid on time.

## How to Use

### Example Request

```bash
curl -X POST "https://your-api-url/v1/score" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
```

### Example Response


```json
{
    "score": 750
}
```

