# **Feedback**

## Overview
The `/v1/feedback` endpoint allows users to provide feedback on the misclassification done by the enrichment endpoints. This feedback is used to improve the accuracy of our enrichments.

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
    "feedback": [
        {
        "api_respone_id": "asdajuefhailejfae",
        "transaction_id": "xa5w46q78yuhdqjlqjmw",
        "error_description": "This is a dining restaurant",
        "incorrect_category": "Groceries",
        "suggested_category": "Food"},
        {
        "api_respone_id": "asdajuefhailejfae",
        "transaction_id": "jougoeujailfmaeau38q",
        "error_description": "this is a gymnastics training center",
        "incorrect_category": "Travel",
        "suggested_category": "Recreation"}
    ]
}
```

***NOTE***
- JSON input with key `feedback` and value is a `list` of `dictionary` of feedbacks,
- Required fields in the dictionary of each feedback are `api_respone_id`, `transaction_id`, `error_description`,
- Optional fields in the dictionary of each feedback are `incorrect_category`, `suggested_category`

### Example Request

- Python
```python
import requests
import json

url = "https://your-api-url/v1/feedback"
headers = {
    "x-api-key": "your_api_key",
    "x-client-id": "your_client_id"
}

data = {
    "feedback": [
        {
        "api_respone_id": "asdajuefhailejfae",
        "transaction_id": "xa5w46q78yuhdqjlqjmw",
        "error_description": "This is a dining restaurant",
        "incorrect_category": "Groceries",
        "suggested_category": "Food"},
        {
        "api_respone_id": "asdajuefhailejfae",
        "transaction_id": "jougoeujailfmaeau38q",
        "error_description": "this is a gymnastics training center",
        "incorrect_category": "Travel",
        "suggested_category": "Recreation"}
    ]
}

response = requests.post(url, headers=headers, data=json.dumps(data))

print(response.json())
```

- Curl
```bash
curl -X POST "https://your-api-url/v1/feedback" \
-H "x-api-key": "your_api_key" \
-H "x-client-id: your_client_id" \
-d "{
    "feedback": [
        {
        "api_respone_id": "asdajuefhailejfae",
        "transaction_id": "xa5w46q78yuhdqjlqjmw",
        "error_description": "This is a dining restaurant",
        "incorrect_category": "Groceries",
        "suggested_category": "Food"},
        {
        "api_respone_id": "asdajuefhailejfae",
        "transaction_id": "jougoeujailfmaeau38q",
        "error_description": "this is a gymnastics training center",
        "incorrect_category": "Travel",
        "suggested_category": "Recreation"}
    ]
}"
```

### Example Response

```json
{
  "feedback_id": [
    "cb359c82-9f97-4e63-a280-bd1a956ecb5e",
    "07745441-f0a6-46fe-9eb0-c0cd2ca1974d"
  ],
  "message": "Feedback data collected successfully"
}
```
