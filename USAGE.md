<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
from nkwa_pay_sdk import Pay
import os


with Pay(
    api_key_auth=os.getenv("PAY_API_KEY_AUTH", ""),
) as pay:

    res = pay.payments.get(id="96e9ed79-9fef-44a6-9435-0625338ca86a")

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asychronous requests by importing asyncio.
```python
# Asynchronous Example
import asyncio
from nkwa_pay_sdk import Pay
import os

async def main():

    async with Pay(
        api_key_auth=os.getenv("PAY_API_KEY_AUTH", ""),
    ) as pay:

        res = await pay.payments.get_async(id="96e9ed79-9fef-44a6-9435-0625338ca86a")

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->