
# Enrich

## Overview
The `/v1/enrich` endpoint enriches transaction data by adding contextual information. This can enhance the value of your dataset by providing additional attributes that can improve analysis and modeling.

## How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - Data can be sent as a JSON file or as JSON data in the request body.
  - The file should be in `.json` format if uploading.

### Example Request
```bash
curl -X POST "https://your-api-url/v1/enrich" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
```
