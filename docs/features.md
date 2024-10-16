# **Features**

## Overview
The `/v1/features` endpoint allows clients to generate features from a provided dataset. It is designed to extract and transform raw data into meaningful features that can be used for further analysis or model training.

## How to Use
- **HTTP Method**: `POST`
- **Headers**:
  - `x-api-key`: Your API key for authorization.
  - `x-client-id`: Your client ID for validation.

- **Request Body**:
  - You can send data either as a JSON file or JSON data in the request body.
  - Ensure that the file is in `.json` format if uploading a file, and the parameter should be `file`.
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
  "features": [
    {
      "cat_bnplpmnt_debit_cnt_1m": 0,
      "cat_bnplpmnt_debit_cnt_1w": 0,
      "cat_bnplpmnt_debit_cnt_3m": 2,
      "cat_bnplpmnt_debit_cnt_6m": 4,
      "cat_bnplpmnt_debit_gt1000_cnt_1m": 0,
      "cat_bnplpmnt_debit_gt1000_cnt_1w": 0,
      "cat_bnplpmnt_debit_gt1000_cnt_3m": 0,
      "cat_bnplpmnt_debit_gt1000_cnt_6m": 0,
      "cat_bnplpmnt_debit_gt100_cnt_1m": 0,
      "cat_bnplpmnt_debit_gt100_cnt_1w": 0,
      "cat_bnplpmnt_debit_gt100_cnt_3m": 2,
      "cat_bnplpmnt_debit_gt100_cnt_6m": 4,
      "cat_bnplpmnt_debit_gt5_cnt_1m": 0,
      "cat_bnplpmnt_debit_gt5_cnt_1w": 0,
      "cat_bnplpmnt_debit_gt5_cnt_3m": 2,
      "cat_bnplpmnt_debit_gt5_cnt_6m": 4,
      "cat_bnplpmnt_debit_le1000_cnt_1m": 0,
      "cat_bnplpmnt_debit_le1000_cnt_1w": 0,
      "cat_bnplpmnt_debit_le1000_cnt_3m": 2,
      "cat_bnplpmnt_debit_le1000_cnt_6m": 4,
      "cat_bnplpmnt_debit_le100_cnt_1m": 0,
      "cat_bnplpmnt_debit_le100_cnt_1w": 0,
      "cat_bnplpmnt_debit_le100_cnt_3m": 0,
      "cat_bnplpmnt_debit_le100_cnt_6m": 0,
      "cat_bnplpmnt_debit_le5_cnt_1m": 0,
      "cat_bnplpmnt_debit_le5_cnt_1w": 0,
      "cat_bnplpmnt_debit_le5_cnt_3m": 0,
      "cat_bnplpmnt_debit_le5_cnt_6m": 0,
      "cat_bnplpmnt_debit_max_1m": null,
      "cat_bnplpmnt_debit_max_1w": null,
      "cat_bnplpmnt_debit_max_3m": 134.73,
      "cat_bnplpmnt_debit_max_6m": 134.73,
      "cat_bnplpmnt_debit_mean_1m": null,
      "cat_bnplpmnt_debit_mean_1w": null,
      "cat_bnplpmnt_debit_mean_3m": 134.73,
      "cat_bnplpmnt_debit_mean_6m": 134.73,
      "cat_bnplpmnt_debit_min_1m": null,
      "cat_bnplpmnt_debit_min_1w": null,
      "cat_bnplpmnt_debit_min_3m": 134.73,
      "cat_bnplpmnt_debit_min_6m": 134.73,
      "cat_bnplpmnt_debit_monthly_amount_stdev_3m": 127.02,
      "cat_bnplpmnt_debit_monthly_amount_stdev_6m": 100.42,
      "cat_bnplpmnt_debit_monthly_count_stdev_3m": 0.94,
      "cat_bnplpmnt_debit_monthly_count_stdev_6m": 0.75,
      "cat_bnplpmnt_debit_std_1m": null,
      "cat_bnplpmnt_debit_std_1w": null,
      "cat_bnplpmnt_debit_std_3m": 0.0,
      "cat_bnplpmnt_debit_std_6m": 0.0,
      "cat_bnplpmnt_debit_sum_1m": 0.0,
      "cat_bnplpmnt_debit_sum_1w": 0.0,
      "cat_bnplpmnt_debit_sum_3m": 269.46,
      "cat_bnplpmnt_debit_sum_6m": 538.92,
      "cat_bnplpmnt_debit_trend_amount_1m_3m": -89.82,
      "cat_bnplpmnt_debit_trend_amount_1m_6m": -89.82,
      "cat_bnplpmnt_debit_trend_count_1m_3m": -0.67,
      "cat_bnplpmnt_debit_trend_count_1m_6m": -0.67,
      "cat_bnplpmnt_debit_trend_mean_1m_3m": null,
      "cat_bnplpmnt_debit_trend_mean_1m_6m": null,
      "ratio_cat_bnplpmnt_debit_by_all_credit_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_all_credit_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_all_credit_3m": 0.01,
      "ratio_cat_bnplpmnt_debit_by_all_debit_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_all_debit_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_all_debit_3m": 0.01,
      "ratio_cat_bnplpmnt_debit_by_allinc_credit_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_allinc_credit_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_allinc_credit_3m": 0.12,
      "ratio_cat_bnplpmnt_debit_by_allrev_credit_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_allrev_credit_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_allrev_credit_3m": 0.03,
      "ratio_cat_bnplpmnt_debit_by_bal_depository_type_acc_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_bal_depository_type_acc_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_bal_depository_type_acc_3m": -1.09,
      "ratio_cat_bnplpmnt_debit_by_dailybal_avg_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_dailybal_avg_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_dailybal_avg_3m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_payroll_1m": 0.0,
      "ratio_cat_bnplpmnt_debit_by_payroll_1w": 0.0,
      "ratio_cat_bnplpmnt_debit_by_payroll_3m": 0.12
    }
  ],
  "metadata": {
    "coverage 1 month": true,
    "coverage 3 months": true,
    "coverage 6 months": true,
    "message": "Success - all features generated",
    "product": "Fincepta Cashflow Data Enrichment"
  }
}
```
</pre>
</div>