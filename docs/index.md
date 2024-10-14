# **Fincepta Cashflow Intelligence**

## Overview
This document outlines the API endpoints available in `Fincepta Cashflow Intelligence`, including their methods, parameters, and expected responses. It serves as a guide for testing the API functionality.

## Base URL
```
http://your-api-url/v1/
```

## Endpoints

### 1. Enrich

Endpoint to enrich transactions with our categories.

### 2. Features

Endpoint to generate features for a given input data

### 3. Score

Endpoint to calculate a score based on the input data, available scores are `cashadvance` and `nsf`.

### 4. Combinations

Combination of multiple endpoints to enrich, generate features and calculate a score based on the input data. A total of 3 combinations are available.

1. Features + Score
2. Features + Enrich
3. Features + Enrich + Score
