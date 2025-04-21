# Payments
(*payments*)

## Overview

### Available Operations

* [get](#get) - Get the payment (collection or disbursement) with the specified ID.
* [collect](#collect) - Collect a payment from a phone number.
* [disburse](#disburse) - Disburse a payment from your balance to a phone number.

## get

Get the payment (collection or disbursement) with the specified ID.

### Example Usage

```python
from nkwa_pay_sdk import Pay
import os


with Pay(
    api_key_auth=os.getenv("PAY_API_KEY_AUTH", ""),
) as pay:

    res = pay.payments.get(id="96e9ed79-9fef-44a6-9435-0625338ca86a")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | ID of payment to fetch                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Payment](../../models/payment.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.HTTPError | 401, 404         | application/json |
| models.HTTPError | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## collect

Collect a payment from a phone number.

### Example Usage

```python
from nkwa_pay_sdk import Pay
import os


with Pay(
    api_key_auth=os.getenv("PAY_API_KEY_AUTH", ""),
) as pay:

    res = pay.payments.collect(amount=433642, phone_number="824.805.0012 x8298")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `amount`                                                            | *int*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `phone_number`                                                      | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Payment](../../models/payment.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.HTTPError | 400, 401, 403    | application/json |
| models.HTTPError | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## disburse

Disburse a payment from your balance to a phone number.

### Example Usage

```python
from nkwa_pay_sdk import Pay
import os


with Pay(
    api_key_auth=os.getenv("PAY_API_KEY_AUTH", ""),
) as pay:

    res = pay.payments.disburse(amount=410119, phone_number="923.242.7389 x02568")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `amount`                                                            | *int*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `phone_number`                                                      | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Payment](../../models/payment.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.HTTPError | 400, 401, 403    | application/json |
| models.HTTPError | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |