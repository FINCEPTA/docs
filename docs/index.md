# CashFlow UW API

## Overview
This document outlines the API endpoints available in `testapp.py`, including their methods, parameters, and expected responses. It serves as a guide for testing the API functionality.

## Base URL
```
http://<your-server-address>:<port>/v1/
```

## Endpoints

### 1. Process Features
- **Endpoint**: `/features`
- **Method**: `POST`
- **Authorization**: Requires `x-api-key` in headers.
- **Permissions**: `can_use_feature`
- **Description**: Processes features from a JSON file or JSON data.
  
#### Request
- **Headers**:
  - `x-api-key`: Your API key.
- **Body** (form-data or JSON):
  - `file`: (optional) Upload a JSON file.
  - `json_data`: (optional) JSON object containing the data.

#### Response
- **200 OK**: Successfully processed features.
- **400 Bad Request**: Invalid file format or no JSON data provided.
- **500 Internal Server Error**: Error processing data.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/features \
  -H 'x-api-key: your_api_key_here' \
  -F 'file=@path/to/your/json/file.json'
```

---

### 2. Enrich Transactions Data
- **Endpoint**: `/enrich`
- **Method**: `POST`
- **Authorization**: Requires `x-api-key` in headers.
- **Permissions**: `can_use_enrich`
- **Description**: Enriches transaction data from a JSON file or JSON data.

#### Request
- **Headers**:
  - `x-api-key`: Your API key.
- **Body** (form-data or JSON):
  - `file`: (optional) Upload a JSON file.
  - `json_data`: (optional) JSON object containing the data.

#### Response
- **200 OK**: Successfully enriched transaction data.
- **400 Bad Request**: Invalid file format or no JSON data provided.
- **500 Internal Server Error**: Error processing data.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/enrich \
  -H 'x-api-key: your_api_key_here' \
  -F 'file=@path/to/your/json/file.json'
```

---

### 3. Get Score
- **Endpoint**: `/score`
- **Method**: `POST`
- **Authorization**: Requires `x-api-key` in headers.
- **Permissions**: `can_use_score`
- **Description**: Retrieves a score from a JSON file or JSON data.

#### Request
- **Headers**:
  - `x-api-key`: Your API key.
- **Body** (form-data or JSON):
  - `file`: (optional) Upload a JSON file.
  - `json_data`: (optional) JSON object containing the data.

#### Response
- **200 OK**: Successfully retrieved score.
- **400 Bad Request**: Invalid file format or no JSON data provided.
- **500 Internal Server Error**: Error processing data.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/score \
  -H 'x-api-key: your_api_key_here' \
  -F 'file=@path/to/your/json/file.json'
```

---

### 4. Get Score with Features
- **Endpoint**: `/score_and_features`
- **Method**: `POST`
- **Authorization**: Requires `x-api-key` in headers.
- **Permissions**: `can_use_score`, `can_use_feature`
- **Description**: Retrieves a score along with features from a JSON file or JSON data.

#### Request
- **Headers**:
  - `x-api-key`: Your API key.
- **Body** (form-data or JSON):
  - `file`: (optional) Upload a JSON file.
  - `json_data`: (optional) JSON object containing the data.

#### Response
- **200 OK**: Successfully retrieved score and features.
- **400 Bad Request**: Invalid file format or no JSON data provided.
- **500 Internal Server Error**: Error processing data.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/score_and_features \
  -H 'x-api-key: your_api_key_here' \
  -F 'file=@path/to/your/json/file.json'
```

---

### 5. Get Features with Enrichment
- **Endpoint**: `/features_and_enrich`
- **Method**: `POST`
- **Authorization**: Requires `x-api-key` in headers.
- **Permissions**: `can_use_feature`, `can_use_enrich`
- **Description**: Retrieves features along with enriched transaction data from a JSON file or JSON data.

#### Request
- **Headers**:
  - `x-api-key`: Your API key.
- **Body** (form-data or JSON):
  - `file`: (optional) Upload a JSON file.
  - `json_data`: (optional) JSON object containing the data.

#### Response
- **200 OK**: Successfully retrieved features and enriched data.
- **400 Bad Request**: Invalid file format or no JSON data provided.
- **500 Internal Server Error**: Error processing data.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/features_and_enrich \
  -H 'x-api-key: your_api_key_here' \
  -F 'file=@path/to/your/json/file.json'
```

---

### 6. Get Score with Features and Enrichment
- **Endpoint**: `/score_and_features_and_enrichment`
- **Method**: `POST`
- **Authorization**: Requires `x-api-key` in headers.
- **Permissions**: `can_use_score`, `can_use_feature`, `can_use_enrich`
- **Description**: Retrieves a score along with features and enriched transaction data from a JSON file or JSON data.

#### Request
- **Headers**:
  - `x-api-key`: Your API key.
- **Body** (form-data or JSON):
  - `file`: (optional) Upload a JSON file.
  - `json_data`: (optional) JSON object containing the data.

#### Response
- **200 OK**: Successfully retrieved score, features, and enriched data.
- **400 Bad Request**: Invalid file format or no JSON data provided.
- **500 Internal Server Error**: Error processing data.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/score_and_features_and_enrichment \
  -H 'x-api-key: your_api_key_here' \
  -F 'file=@path/to/your/json/file.json'
```

---

### 7. Generate API Key
- **Endpoint**: `/generate_api_key`
- **Method**: `POST`
- **Description**: Generates a new API key for a client.

#### Request
- **Body** (JSON):
  - `client_name`: Name of the client.
  - `email`: Email of the client.
  - `client_id`: Unique identifier for the client.
  - `can_use_feature`: (optional) Boolean indicating if the client can use features.
  - `can_use_enrich`: (optional) Boolean indicating if the client can use enrichment.
  - `can_use_score`: (optional) Boolean indicating if the client can use scoring.
  - `model_access`: (optional) JSON object for model access.
  - `enrich_limit`: (optional) Limit for enrichment requests.
  - `feature_limit`: (optional) Limit for feature requests.
  - `score_limit`: (optional) Limit for score requests.

#### Response
- **201 Created**: Successfully generated API key.
- **400 Bad Request**: Missing required fields.

#### Example Request using curl
```bash
curl -X POST \
  http://<your-server-address>:<port>/v1/generate_api_key \
  -H 'Content-Type: application/json' \
  -d '{"client_name": "Your Client Name", "email": "your_email@example.com", "client_id": "your_client_id"}'
```

---

## Error Handling
All endpoints return appropriate error messages and status codes for various failure scenarios, including unauthorized access, bad requests, and internal server errors.

---

## Notes
- Ensure that the API key is included in the headers for all requests that require authorization.
- The API expects JSON formatted data for most endpoints, and file uploads should be in JSON format as well.