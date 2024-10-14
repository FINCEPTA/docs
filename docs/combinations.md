# Combinations

## Features and Enrich Endpoint

### Overview
The `/v1/features_and_enrich` endpoint allows clients to simultaneously generate features and enrich transaction data. This combined approach can save time and streamline workflows by providing enriched features in a single request.

### How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - Data can be submitted as a JSON file or in JSON format in the request body.
  - Ensure that any uploaded file is in `.json` format.

#### Example Request
```bash
curl -X POST "https://your-api-url/v1/features_and_enrich" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
```
## Features and Score Endpoint

### Overview
The `/v1/score_and_features` endpoint allows clients to generate features from their dataset while simultaneously calculating a score. This combined functionality streamlines the process of transforming raw data into valuable insights, essential for predictive modeling and risk assessment.

### How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - You can submit your data as a JSON file or directly as JSON in the request body.
  - If uploading a file, ensure it is in `.json` format.

#### Example Request
```bash
curl -X POST "https://your-api-url/v1/score_and_features" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
```

## Features, Enrichment, and Score Endpoint

### Overview
The `/v1/score_and_features_and_enrichment` endpoint allows clients to generate features, enrich their data, and calculate a score all in one request. This comprehensive approach is ideal for complex data processing needs.

### How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - Data can be sent as a JSON file or JSON data in the request body.
  - Ensure that the file is in `.json` format if uploading.

#### Example Request
```bash
curl -X POST "https://your-api-url/v1/score_and_features_and_enrichment" \
-H "x-api-key: your_api_key" \
-H "x-client-id: your_client_id" \
-F "file=@path_to_your_file.json"
```