# Crypto

### Track Shitcoin Pricing with Google Sheets

1. Access [https://coinmarketcap.com/api/](https://coinmarketcap.com/api/) to get the API key.
2. Open a Google Sheets spreadsheet and select the menu item `Tools -> Script editor`.
3. Created the function called “crypto” which takes ticker of cryptocurrency as an argument and return current price as USD:

```text
function crypto(ticker) {
 
  var url = "https://pro-api.coinmarketcap.com/v1/cryptocurrency/quotes/latest?symbol=" + ticker;
  var requestOptions = {
    method: 'GET',
    uri: 'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest',
    qs: {
      start: 1,
      limit: 5000,
      convert: 'USD'
    },
    headers: {
      'X-CMC_PRO_API_KEY': 'Your_API_key_is_here'
    },
    json: true,
    gzip: true
  };
  var result = UrlFetchApp.fetch(url, requestOptions);
 
  var txt = result.getContentText(); // JSON as a text
  var jsonData = JSON.parse(txt);
  var path = "jsonData.data." + ticker + ".quote.USD.price"; // path to the current price
  var price = eval(path);
 
  return price;
 
}
```

![Usage example](../.gitbook/assets/crypto2-1.png)

* You might want to refer the official API document: [https://coinmarketcap.com/api/documentation/v1/](https://coinmarketcap.com/api/documentation/v1/) to know detail.
* [https://elasticforest.com/2020/09/20/track-shitcoin-pricing-with-google-sheets/](https://elasticforest.com/2020/09/20/track-shitcoin-pricing-with-google-sheets/)

