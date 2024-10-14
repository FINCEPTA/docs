# Features

## Overview
The `/v1/features` endpoint allows clients to generate features from a provided dataset. It is designed to extract and transform raw data into meaningful features that can be used for further analysis or model training.

## How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - You can send data either as a JSON file or JSON data in the request body.
  - Ensure that the file is in `.json` format if uploading a file.

### Example Request
```bash
curl -X POST "https://your-api-url/v1/features" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
```