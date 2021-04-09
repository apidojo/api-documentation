---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - Visit our website at <a href='https://apidojo.net'>apidojo.net</a> for more information

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the API Dojo documentation! You can use our APIs to access official live and structural data from lots of brands which are from various categories.

We currently provide our services via <a href='https://rapidapi.com'>RapidAPI</a> only. You need to register an account on the market platform as developer or consumer to start using our APIs. Please have a look at <a href='https://docs.rapidapi.com/docs/basics-creating-a-project'>Creating a project</a> to get started.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-rapidapi-key: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

RapidAPI uses token key to allow access to all APIs on the platform. You need to generate a token key for a new app in your developer control panel of RapidAPI at https://rapidapi.com/developer. 

You then need to learn how to pass the token key via request HEADER as following :

`x-rapidapi-key: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Bloomberg API

## Market

### market/auto-complete

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/auto-complete?query=tesla" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "quote": [
        {
            "securityType": "Common Stock",
            "symbol": "TSLA",
            "exchange": "NASDAQ GS",
            "country": "United States",
            "currency": "USD",
            "resourceType": "Company",
            "fundamentalDataCurrency": "USD",
            "resourceSubtype": "Public",
            "region": "AMERICAS",
            "ticker": "tsla:us",
            "tickerName": "TSLA:US",
            "template": "Stock",
            "tinyName": "Tesla Inc",
            "name": "Tesla Inc",
            "watchlist": true,
            "resourceId": "TSLA:US",
            "id": "TSLA:US",
            "title": "Tesla Inc",
            "card": "security"
        },
        ...
    ],
    "news": [
        {
            "title": "Panasonic Bets on Tesla ‘Beer Can’ Battery to Unlock $25,000 EVs",
            "id": "QQVW38DWLU7D01",
            "card": "article",
            "date": 1617930075,
            "longURL": "https://www.bloomberg.com/news/articles/2021-04-08/panasonic-bets-on-tesla-beer-can-battery-to-unlock-25-000-evs"
        },
        ...
    ]
}
```

This endpoint queries suggestion by term and phrase.

#### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/auto-complete`

#### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
query | String | Any thing you are familiar with, stock, index, organization, etc...

### market/get-movers

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-movers?id=ndx:ind" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "active": [
        {
            "securityType": "Common Stock",
            "symbol": "AAPL",
            "exchange": "NASDAQ GS",
            "country": "United States",
            "currency": "USD",
            "resourceType": "Company",
            "fundamentalDataCurrency": "USD",
            "resourceSubtype": "Public",
            "region": "AMERICAS",
            "ticker": "aapl:us",
            "tickerName": "AAPL:US",
            "template": "Stock",
            "tinyName": "Apple Inc",
            "name": "Apple Inc",
            "watchlist": true,
            "resourceId": "AAPL:US",
            "last": "130.36",
            "netChange": "2.46",
            "lastPriceTime": 1617854400,
            "pctChange1M": "7.66",
            "yearHigh": "145.09",
            "dayHigh": "130.39",
            "volume": 88844591,
            "yearLow": "66.17",
            "dayLow": "128.52",
            "pctChangeYTD": "-1.76",
            "lastPriceAllSessions": "129.80",
            "pctChange": "1.92"
        },
        ...
    ],
    "laggards": [
        {
            "securityType": "Common Stock",
            "symbol": "WBA",
            "exchange": "NASDAQ GS",
            "country": "United States",
            "currency": "USD",
            "resourceType": "Company",
            "fundamentalDataCurrency": "USD",
            "resourceSubtype": "Public",
            "region": "AMERICAS",
            "ticker": "wba:us",
            "tickerName": "WBA:US",
            "template": "Stock",
            "tinyName": "Walgreens Boots Alliance Inc",
            "name": "Walgreens Boots Alliance Inc",
            "watchlist": true,
            "resourceId": "WBA:US",
            "last": "54.79",
            "netChange": "-0.79",
            "lastPriceTime": 1617854400,
            "pctChange1M": "13.06",
            "yearHigh": "57.05",
            "dayHigh": "55.39",
            "volume": 5879775.0,
            "yearLow": "33.36",
            "dayLow": "54.48",
            "pctChangeYTD": "37.39",
            "lastPriceAllSessions": "54.83",
            "pctChange": "-1.42"
        },
        ...
    ],
    "leaders": [
        {
            "securityType": "Common Stock",
            "symbol": "PTON",
            "exchange": "NASDAQ GS",
            "country": "United States",
            "currency": "USD",
            "resourceType": "Company",
            "fundamentalDataCurrency": "USD",
            "resourceSubtype": "Public",
            "region": "AMERICAS",
            "ticker": "pton:us",
            "tickerName": "PTON:US",
            "template": "Stock",
            "tinyName": "Peloton Interactive Inc",
            "name": "Peloton Interactive Inc",
            "watchlist": true,
            "resourceId": "PTON:US",
            "last": "123.62",
            "netChange": "8.42",
            "lastPriceTime": 1617854400,
            "pctChange1M": "6.55",
            "yearHigh": "171.09",
            "dayHigh": "124.50",
            "volume": 14751521,
            "yearLow": "27.32",
            "dayLow": "116.63",
            "pctChangeYTD": "-18.52",
            "lastPriceAllSessions": "124.15",
            "pctChange": "7.31"
        },
        ...
    ]
}
```

Get latest information of movers in the market.

#### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-movers`

#### URL Parameters

Parameter | Description
--------- | -----------
id | The value of id field returned in .../market/auto-complete endpoint.
