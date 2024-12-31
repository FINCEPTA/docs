# **Fincepta Cashflow Intelligence**

## Overview
This document outlines the API endpoints available in `Fincepta Cashflow Intelligence`, including their methods, parameters, and expected responses. It serves as a guide for testing the API functionality.

## Base URL
```
https://cfil.fincepta.com/{client_id}/
```

## Endpoints

### 1. Enrich

Endpoint to enrich bank transactions with categorization & recurrence.

### 2. Features

Endpoint to generate features for a report. These features cover insights (on assets, liabilities & cashflows) & complex risk predictive features.

### 3. Score

Endpoint to generate a risk score based on the input report, available scores are `cashadvance` and `nsf`.

### 4. Combinations

Combination of multiple endpoints to enrich, generate features and scores based on the input data. A total of 3 combinations are available.

1. Features + Score
2. Features + Enrich
3. Features + Enrich + Score
