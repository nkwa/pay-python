# Service
(*service*)

## Overview

### Available Operations

* [availability](#availability) - Check which operators and operations are currently available.

## availability

Check which operators and operations are currently available.

### Example Usage

```python
from nkwa_pay_sdk import Pay
import os


with Pay(
    api_key_auth=os.getenv("PAY_API_KEY_AUTH", ""),
) as pay:

    res = pay.service.availability()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[models.Availability]](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.HTTPError | 401              | application/json |
| models.HTTPError | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |