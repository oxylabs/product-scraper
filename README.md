# Product Scraper API

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)

Oxylabs’ [Product Scraper](https://oxylabs.io/products/scraper-api/web/product-scraper?utm_source=github&utm_medium=repositories&utm_campaign=product) is a data gathering solution allowing you to extract real-time information from various online sources website effortlessly. This brief guide explains how Product Scraper works and provides code examples to understand better how you can use it hassle-free.

### How it works

You can get HTML results by providing your own URLs to our service. We can return the HTML for any product page you like.

#### Python code example

The example below illustrates how you can get HTML of a [bellroy.com](https://bellroy.com/products/slim-sleeve-wallet?color=cocoa-java&material=leather&size=default) product page.

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal',
    'url': 'https://bellroy.com/products/slim-sleeve-wallet?color=cocoa-java&material=leather&size=default'
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```
Find code examples for other programming languages [**here**](https://github.com/oxylabs/product-scraper/tree/main/code%20examples)

#### Output Example
```json
{
  "results": [
    {
      "content": "<!DOCTYPE html>\n<!--[if lt IE 9]> <html class=\"old-ie\"> <![endif]-->\n<!--[if IE 9]> <html class=\"ie- ... </html>",
      "created_at": "2023-12-18 11:21:56",
      "updated_at": "2023-12-18 11:21:58",
      "page": 1,
      "url": "https://bellroy.com/products/slim-sleeve-wallet?color=cocoa-java&material=leather&size=default",
      "job_id": "7142474058171445249",
      "status_code": 200
    }
  ]
}
```
With our Shoe Scraper, you can effortlessly extract public data from any footwear web page. Gather the desired product information, such as price, customer reviews, or detailed product descriptions, to evaluate the footwear market and always stay one step ahead of your competitors. If you have any queries, feel free to contact our supportive team via live chat or you can also drop us an email at hello@oxylabs.io.
