---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - Visit our website at <a href='https://apidojo.net' target='_blank'>apidojo.net</a><br/>
  for all available APIs

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the API Dojo documentation! You can use our APIs to access official live and structural data from lots of brands which are from various categories. You may check all available APIs at <a href='https://apidojo.net/api-of-brands/' target='_blank'>APIDojo.net</a>

We currently provide our services via <a href='https://rapidapi.com/search/apidojo' target='_blank'>RapidAPI</a> only. You need to register an account on the market platform as developer or consumer to start using our APIs. Please have a look at <a href='https://docs.rapidapi.com/docs/basics-creating-a-project'  target='_blank'>Creating a project</a> to get started.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-rapidapi-key: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

RapidAPI uses token key to allow access to all APIs on the platform. You need to generate a token key for a new app in your developer control panel of RapidAPI at <a href='https://rapidapi.com/developer' target='_blank'>https://rapidapi.com/developer</a>. 

You then need to learn how to pass the token key via request HEADER as following :

`x-rapidapi-key: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Redirected issues

Some of our private APIs get redirected to other links because of new update made by RapidAPI. Please see the short video clip at <a href='https://www.youtube.com/watch?v=Ypf_938bJzA'  target='_blank'>https://www.youtube.com/watch?v=Ypf_938bJzA</a> to know how to overcome this issue and access the API normally.

We have reported the issue to RapidAPI, we need to wait for them and a hot fix released.

# Bloomberg API

## market/auto-complete

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

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/auto-complete`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
query | string (required) | Any thing you are familiar with, stock, index, organization, etc...

## market/get-movers

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

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-movers`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint.

## market/get-cross-currencies

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-cross-currencies?id=aed,aud,brl,cad,chf,cnh,cny,cop,czk,dkk,eur,gbp,hkd,huf,idr,ils,inr,jpy,krw,mxn,myr,nok,nzd,php,pln,rub,sek,sgd,thb,try,twd,usd,zar" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
  "result": {
    "MXNJPY:cur": {
      "baseName": "JAPANESE YEN",
      "securityType": "CROSS",
      "symbol": "MXNJPY",
      "country": "Japan",
      "currency": "JPY",
      "resourceType": "Currency",
      "resourceSubtype": "Cross",
      "region": "APAC",
      "ticker": "mxnjpy:cur",
      "tickerName": "MXNJPY:CUR",
      "template": "Currency",
      "tinyName": "MXN-JPY",
      "name": "MXNJPY Spot Exchange Rate - Price of 1 MXN in JPY",
      "watchlist": true,
      "resourceId": "MXNJPY:CUR",
      "last": "5.4411",
      "netChange": "0.0039",
      "lastPriceTime": 1617965922,
      "yearHigh": "5.4632",
      "dayHigh": "5.4447",
      "yearLow": "4.2501",
      "sourceCurrency": "MXN",
      "dayLow": "5.4173",
      "pctChange": "0.07"
    },
    ...
  }
}
```

Get exchange rate between currencies.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-cross-currencies`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The currency code, separated by comma to query multiple currencies at once

## market/get-price-chart

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-price-chart?id=INMEX:IND&interval=d1" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
  "result": {
    "INMEX:IND": {
      "first": 1617888600,
      "last": 1617912600,
      "historical": false,
      "ticksType": "MinuteTick",
      "ticks": [
        {
          "time": 1617888600,
          "close": 2968.67,
          "volume": 0
        },
        ...
      ],
      "low": "2962.48",
      "high": "2992.06",
      "hasVolume": true,
      "security": {
        "ticker": "INMEX:IND",
        "open": "2962.47",
        "prevClose": "2964.31"
      }
    }
  }
}
```

Get data to draw historical price chart.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-price-chart`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint.
interval | string (required) | One of the followings : d1 &#124; d3 &#124; ytd &#124; m1 &#124; m3 &#124; m6 &#124; y1 &#124; y5

## market/get-full

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-full?id=AAPL:US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "result": {
        "AAPL:US": {
            "info": "Apple Inc. designs, manufactures, and markets personal computers and related personal computing and mobile communication devices along with a variety of related software, services, peripherals, and networking solutions. Apple sells its products worldwide through its online stores, its retail stores, its direct sales force, third-party wholesalers, and resellers.",
            "securityType": "Common Stock",
            "symbol": "AAPL",
            "exchange": "NASDAQ GS",
            "currency": "USD",
            "resourceType": "Company",
            "fundamentalDataCurrency": "USD",
            "resourceSubtype": "Public",
            "website": "www.apple.com",
            "phone": "1-408-996-1010",
            "address": "1 Infinite Loop\nCupertino, CA 95014\nUnited States",
            "region": "AMERICAS",
            "ticker": "aapl:us",
            "tickerName": "AAPL:US",
            "template": "Stock",
            "name": "Apple Inc",
            "executives": [
                {
                    "id": "14014370",
                    "title": "Chief Executive Officer",
                    "name": "Timothy Donald Cook \"Tim\"",
                    "thumbnailImage": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/iOIEqOOiLpFY/v3/80x80.jpg",
                    "tenureStart": "8/2011"
                },
                ...
            ],
            "watchlist": true,
            "resourceId": "AAPL:US",
            "totalReturn1Y": "96.08",
            "subSector": "Technology Hardware",
            "last": "130.36",
            "netChange": "2.46",
            "lastPriceTime": 1617854400,
            "peRatio": "35.39",
            "open": "128.95",
            "close": "127.90",
            "industry": "Tech Hardware & Semiconductors",
            "yearHigh": "145.09",
            "dayHigh": "130.39",
            "volume": 88844591,
            "sector": "Technology",
            "yearLow": "66.17",
            "dayLow": "128.52",
            "marketCap": 2188496194560.0002,
            "lastPriceAllSessions": "130.20",
            "pctChange": "1.92",
            "sectorPercentChange1Day": "1.42",
            "industryPercentChange1Day": "1.64"
        }
    }
}
```

Get all field and information about indices, commodities, currencies, rates, etc...

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-full`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint, separated by comma to query multiple stickers at once.

## market/get-compact

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-compact?id=AAPL:US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "result": {
        "AAPL:US": {
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
            "lastPriceAllSessions": "130.16",
            "pctChange": "1.92"
        }
    }
}
```

Get most informative fields about indices, commodities, currencies, rates, etc...

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-compact`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint, separated by comma to query multiple stickers at once.

## market/get-chart

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-chart?id=INMEX:IND&interval=d1" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "result": {
        "INMEX:IND": {
            "first": 1617888600,
            "last": 1617912600,
            "historical": false,
            "ticksType": "MinuteTick",
            "ticks": [
                {
                    "time": 1617888600,
                    "close": 2968.67,
                    "volume": 0
                },
                ...
            ],
            "low": "2962.48",
            "high": "2992.06",
            "hasVolume": true,
            "security": {
                "ticker": "INMEX:IND",
                "open": "2962.47",
                "prevClose": "2964.31"
            }
        }
    }
}
```

Get related data for drawing chart.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/market/get-chart`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint
interval | string (required) | One of the followings : d1 &#124; d3 &#124; ytd &#124; m1 &#124; m3 &#124; m6 &#124; y1 &#124; y5

## stock/get-statistics

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/stock/get-statistics?id=TSLA:US&template=STOCK" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "result": [
        {
            "name": "Key Statistics",
            "table": [
                {
                    "name": "Current P/E Ratio (ttm)",
                    "value": "924.82"
                },
                {
                    "name": "Estimated P/E",
                    "value": "158.95",
                    "comment": "(2021-12)"
                },
                {
                    "name": "Relative P/E",
                    "value": "27.81",
                    "comment": "vs SPX:IND"
                },
                {
                    "name": "Earnings Per Share (ttm)",
                    "value": "0.74"
                },
                {
                    "name": "Est. EPS",
                    "value": "4.30",
                    "comment": "(2021-12)"
                },
                {
                    "name": "Est. PEG Ratio",
                    "value": "3.91"
                },
                {
                    "name": "Market Cap (M)",
                    "value": "656,347.83"
                },
                {
                    "name": "Shares Outstanding (M)",
                    "value": "959.85"
                },
                {
                    "name": "Price/Book (mrq)",
                    "value": "29.54"
                },
                {
                    "name": "Price/Sales (ttm)",
                    "value": "20.30"
                },
                {
                    "name": "Next Earnings Announcement",
                    "value": "2021-04-29"
                },
                {
                    "name": "Average Volume (30-day)",
                    "value": "39,281,468"
                }
            ]
        }
    ]
}
```

Get statistics information of stocks, indices,etc...

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/stock/get-statistics`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint
template | string | One of the following COMMODITY &#124; CURRENCY &#124; INDEX &#124; INDEXFUTURE &#124; RATE &#124; STOCK

## stock/get-financials

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/stock/get-financials?id=TSLA:US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "result": [
        {
            "name": "Income Statement",
            "securityID": "TSLA:US",
            "timeBasedSheets": [
                {
                    "name": "Quarterly",
                    "columnHeadings": [
                        "6/2020",
                        "9/2020",
                        "12/2020"
                    ],
                    "chartData": [
                        {
                            "name": "Revenue",
                            "chartType": "bar",
                            "isPercentage": false,
                            "values": [
                                6.036E9,
                                8.771E9,
                                1.0744E10
                            ]
                        },
                        ...
                    ]
                },
                {
                    "name": "Annual",
                    "columnHeadings": [
                        "2017",
                        "2018",
                        "2019",
                        "2020"
                    ],
                    "chartData": [
                        {
                            "name": "Revenue",
                            "chartType": "bar",
                            "isPercentage": false,
                            "values": [
                                1.1758751E10,
                                2.1461268E10,
                                2.4578E10,
                                3.1536E10
                            ]
                        },
                        ...
                    ]
                }
            ]
        },
        {
            "name": "Balance Sheet",
            "securityID": "TSLA:US",
            "timeBasedSheets": [
                {
                    "name": "Quarterly",
                    "columnHeadings": [
                        "6/2020",
                        "9/2020",
                        "12/2020"
                    ],
                    "chartData": [
                        {
                            "name": "Total Assets",
                            "chartType": "bar",
                            "isPercentage": false,
                            "values": [
                                3.8135E10,
                                4.5691E10,
                                5.2148E10
                            ]
                        },
                        ...
                    ]
                },
                {
                    "name": "Annual",
                    "columnHeadings": [
                        "2017",
                        "2018",
                        "2019",
                        "2020"
                    ],
                    "chartData": [
                        {
                            "name": "Total Assets",
                            "chartType": "bar",
                            "isPercentage": false,
                            "values": [
                                2.8655372E10,
                                2.9739614E10,
                                3.4309E10,
                                5.2148E10
                            ]
                        },
                        ...
                    ]
                }
            ]
        },
        {
            "name": "Cash Flow",
            "securityID": "TSLA:US",
            "timeBasedSheets": [
                {
                    "name": "Quarterly",
                    "columnHeadings": [
                        "6/2020",
                        "9/2020",
                        "12/2020"
                    ],
                    "chartData": [
                        {
                            "name": "Operating",
                            "chartType": "line",
                            "isPercentage": false,
                            "values": [
                                9.64E8,
                                2.4E9,
                                3.019E9
                            ]
                        },
                        ...
                    ]
                },
                {
                    "name": "Annual",
                    "columnHeadings": [
                        "2017",
                        "2018",
                        "2019",
                        "2020"
                    ],
                    "chartData": [
                        {
                            "name": "Operating",
                            "chartType": "line",
                            "isPercentage": false,
                            "values": [
                                -6.0654E7,
                                2.0978020000000002E9,
                                2.405E9,
                                5.943E9
                            ]
                        },
                        ...
                    ]
                }
            ]
        }
    ]
}
```

Get financial information of stocks.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/stock/get-financials`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint

## news/list

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/news/list?id=markets" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "title": "Bloomberg Markets",
    "modules": [
        {
            "id": "hero_1",
            "title": null,
            "type": "single_story",
            "tracking": {
                "id": "36ba25c6-8f14-472a-8068-75b40b7ec2dc",
                "title": "Hero"
            },
            "stories": [
                {
                    "id": "2021-04-08/asia-stocks-set-for-steady-open-treasuries-climb-markets-wrap",
                    "internalID": "QR9J4WT0AFB401",
                    "title": "U.S. Futures Fluctuate as Treasury Yields Rise: Markets Wrap",
                    "summary": "",
                    "autoGeneratedSummary": "U.S. equity-index futures struggled for direction on Friday as investors weighed prospects for economic growth against lingering inflation concerns. Treasury yields rose and the dollar gained.",
                    "abstract": [
                        "Italian yields jump on borrowing plans; dollar index gains",
                        "Europe stocks headed for sixth weekly rise; oil dips"
                    ],
                    "published": 1617920145,
                    "updatedAt": 1617966895,
                    "wordCount": 501,
                    "secondaryBrands": [
                        "markets"
                    ],
                    "byline": "Emily Barrett and Robert Brand",
                    "shortURL": "https://www.bloomberg.com/news/articles/2021-04-08/asia-stocks-set-for-steady-open-treasuries-climb-markets-wrap",
                    "longURL": "https://www.bloomberg.com/news/articles/2021-04-08/asia-stocks-set-for-steady-open-treasuries-climb-markets-wrap",
                    "primaryCategory": "Markets",
                    "primarySite": "markets",
                    "eyebrowSite": "markets",
                    "readings": [
                        {
                            "url": "https://assets.bwbx.io/s3/readings/QRAMIET0AFBE1617966895879.mp3",
                            "voice": "Matthew",
                            "durationMs": 213760
                        }
                    ],
                    "image": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ivdAgOgTiO1s/v0/600x-1.jpg",
                    "thumbnailImage": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ivdAgOgTiO1s/v0/360x-1.jpg",
                    "card": "article",
                    "contentTags": [
                        {
                            "id": "industrial-production",
                            "type": "Topic"
                        },
                        ...
                    ],
                    "meta": {
                        "newsletterToutLabel": null,
                        "newsletterSlug": null
                    }
                },
                ...
            ]
        },
        ...
    ]
}
```

List news by category.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/news/list`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | One of the following is allowed markets &#124; technology &#124; view &#124; pursuits &#124; politics &#124; green &#124; citylab &#124; businessweek &#124; fixed-income &#124; hyperdrive &#124; cryptocurrencies &#124; wealth &#124; latest &#124; personalFinance &#124; quickTake &#124; world &#124; industries &#124; stocks &#124; currencies &#124; brexit

## news/list-by-region

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/news/list-by-region?id=asia-home-v3" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "title": null,
    "id": "asia-home-v3",
    "indexBar": {
        "enabled": true,
        "quotes": [
            {
                "INDU:IND": {
                    "securityType": "Equity Index",
                    "symbol": "INDU",
                    "country": "United States",
                    "currency": "USD",
                    "resourceType": "Index",
                    "fundamentalDataCurrency": "USD",
                    "resourceSubtype": "Equity",
                    "region": "AMERICAS",
                    "ticker": "indu:ind",
                    "tickerName": "INDU:IND",
                    "template": "Index",
                    "tinyName": "DOW JONES",
                    "name": "DOW JONES",
                    "watchlist": true,
                    "resourceId": "INDU:IND",
                    "eqtIndex": true,
                    "last": "33503.57",
                    "netChange": "57.31",
                    "lastPriceTime": 1617854400,
                    "pctChange1M": "5.25",
                    "yearHigh": "33617.95",
                    "dayHigh": "33506.80",
                    "volume": 8.452485E+7,
                    "yearLow": "22682.99",
                    "dayLow": "33342.64",
                    "pctChangeYTD": "9.47",
                    "pctChange": "0.17",
                    "isOpen": false,
                    "sparkline": {
                        "href": "https://www.bloomberg.com/markets/api/charts/sparkline/INDU:IND.svg?stroke=2"
                    }
                }
            },
            ...
        ],
        "stories": [
            {
                "id": "2021-04-08/asia-stocks-set-for-steady-open-treasuries-climb-markets-wrap",
                "internalID": "QR9J4WT0AFB401",
                "title": "U.S. Futures Fluctuate as Treasury Yields Rise: Markets Wrap",
                "summary": "",
                "autoGeneratedSummary": "U.S. equity-index futures struggled for direction on Friday as investors weighed prospects for economic growth against lingering inflation concerns. Treasury yields rose and the dollar gained.",
                "abstract": [
                    "Italian yields jump on borrowing plans; dollar index gains",
                    "Europe stocks headed for sixth weekly rise; oil dips"
                ],
                "published": 1617920145,
                "updatedAt": 1617966895,
                "wordCount": 501,
                "secondaryBrands": [
                    "markets"
                ],
                "byline": "Emily Barrett and Robert Brand",
                "shortURL": "https://www.bloomberg.com/news/articles/2021-04-08/asia-stocks-set-for-steady-open-treasuries-climb-markets-wrap",
                "longURL": "https://www.bloomberg.com/news/articles/2021-04-08/asia-stocks-set-for-steady-open-treasuries-climb-markets-wrap",
                "primaryCategory": "Markets",
                "primarySite": "markets",
                "eyebrowSite": "markets",
                "readings": [
                    {
                        "url": "https://assets.bwbx.io/s3/readings/QRAMIET0AFBE1617966895879.mp3",
                        "voice": "Matthew",
                        "durationMs": 213760
                    }
                ],
                "image": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ivdAgOgTiO1s/v0/600x-1.jpg",
                "thumbnailImage": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ivdAgOgTiO1s/v0/360x-1.jpg",
                "card": "article",
                "contentTags": [
                    {
                        "id": "industrial-production",
                        "type": "Topic"
                    },
                    ...
                ],
                "meta": {
                    "newsletterToutLabel": null,
                    "newsletterSlug": null
                }
            }
        ]
    },
    "modules": [
        {
            "id": "hfs",
            "title": null,
            "type": "single_story",
            "mobileMaximum": "1",
            "tracking": {
                "id": "88cf9e25-dace-4e4e-a85e-3752a533c5ec",
                "title": "HFS"
            },
            "stories": [
                {
                    "id": "2021-04-09/when-will-world-be-fully-vaccinated-pace-is-2-400-faster-in-wealthy-countries",
                    "internalID": "QRA35ZDWRGG101",
                    "title": "The World’s Wealthiest Countries Are Getting Vaccinated 25 Times Faster",
                    "summary": "Economies with the highest incomes have 40% of the world’s vaccinations, but just 11% of the global population",
                    "autoGeneratedSummary": "",
                    "abstract": [],
                    "published": 1617940871,
                    "updatedAt": 1617940871,
                    "wordCount": 475,
                    "franchise": "prognosis",
                    "secondaryBrands": [
                        "business",
                        "equality",
                        "politics"
                    ],
                    "byline": "Tom Randall",
                    "shortURL": "https://www.bloomberg.com/news/articles/2021-04-09/when-will-world-be-fully-vaccinated-pace-is-2-400-faster-in-wealthy-countries",
                    "longURL": "https://www.bloomberg.com/news/articles/2021-04-09/when-will-world-be-fully-vaccinated-pace-is-2-400-faster-in-wealthy-countries",
                    "primaryCategory": "World",
                    "primarySite": "bbiz",
                    "eyebrowSite": "bbiz",
                    "readings": [
                        {
                            "url": "https://assets.bwbx.io/s3/readings/QRA35ZDWRGG11617969809699.mp3",
                            "voice": "Matthew",
                            "durationMs": 182309
                        }
                    ],
                    "image": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ifp2ch1F6X1E/v0/600x-1.png",
                    "thumbnailImage": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ifp2ch1F6X1E/v0/360x-1.png",
                    "card": "article",
                    "contentTags": [
                        {
                            "id": "CN",
                            "type": "Country"
                        },
                        ...
                    ],
                    "meta": {
                        "newsletterToutLabel": null,
                        "newsletterSlug": null
                    }
                }
            ]
        },
        ...
    ]
}
```

List latest news from different categories and grouped by region.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/news/list-by-region`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | One of the followings : home-v3 &#124; asia-home-v3 &#124; europe-home-v3 &#124; middle-east-home-v3 &#124; africa-home-v3 &#124; canada-home-v3

## stories/list

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/stories/list?id=usdjpy&template=CURRENCY" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "stories": [
        {
            "resourceType": "Story",
            "card": "article",
            "title": "Saudi Expansion in Focus for Paymob After Record Egypt Fundraise",
            "published": 1617876215,
            "internalID": "QR6O42DWX2PY01",
            "thumbnailImage": "https://assets.bwbx.io/images/users/iqjWHBFdfxIU/i6RQ802xNIQ4/v0/600x-1.jpg",
            "primarySite": "technology",
            "shortURL": "https://www.bloomberg.com/news/articles/2021-04-08/egypt-s-paymob-eyes-saudi-market-as-cashless-transactions-surge",
            "longURL": "https://www.bloomberg.com/news/articles/2021-04-08/egypt-s-paymob-eyes-saudi-market-as-cashless-transactions-surge"
        },
        ...
    ],
    "title": "Currencies"
}
```

Get a list of stories related to a sticker.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/stories/list`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | The value of id field returned in .../market/auto-complete endpoint
template | string | One of the followings : COMMODITY &#124; CURRENCY &#124; INDEX &#124; INDEXFUTURE &#124; RATE &#124; STOCK

## stories/detail

```shell
curl "https://bloomberg-market-and-financial-news.p.rapidapi.com/stories/detail?internalID=QFY0Y6T0AFB501" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: bloomberg-market-and-financial-news.p.rapidapi.com"
```

Get full story.

### HTTP Request

`GET https://bloomberg-market-and-financial-news.p.rapidapi.com/stories/detail`

### URL Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
internalID | string (required) | Get suitable value from .../stories/list or .../news/list or .../news/list-by-region endpoints

# Realtor API

## locations/auto-complete

```shell
curl "https://realtor.p.rapidapi.com/locations/auto-complete?input=11160 Trails End Ct, Rancho Cucamonga CA 91737" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150"
    },
    "autocomplete": [
        {
            "area_type": "address",
            "_id": "addr:1658306335",
            "_score": 10281.245,
            "mpr_id": "1658306335",
            "full_address": [
                "11160 Trails End Ct Rancho Cucamonga CA 91737",
                "11160 Trails End Ct Rancho Cucamonga CA"
            ],
            "line": "11160 Trails End Ct",
            "city": "Rancho Cucamonga",
            "postal_code": "91737",
            "state_code": "CA",
            "country": "USA",
            "centroid": {
                "lon": -117.56178,
                "lat": 34.151592
            },
            "prop_status": [
                "recently_sold",
                "not_for_sale"
            ],
            "validation_code": [
                "121"
            ]
        },
        {
            "area_type": "postal_code",
            "_id": "ps:ca_91737",
            "_score": 23.913471,
            "postal_code": "91737",
            "state_code": "CA",
            "city": "Rancho Cucamonga",
            "country": "USA",
            "centroid": {
                "lon": -117.58736,
                "lat": 34.17892
            },
            "slug_id": "91737",
            "geo_id": "4b49d7a1-a0b2-5dc0-aea0-a87cc86abb62"
        }
    ]
}
```

This endpoint is used to get auto complete suggestions by city, ward, street name to pass in other endpoints. This endpoint also helps to get a specific property id by its address

### HTTP Request

`GET https://realtor.p.rapidapi.com/locations/auto-complete`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
input | string (required) | Name of cities, districts, places, or addresses etc...

## mortgage/calculate

```shell
curl "https://realtor.p.rapidapi.com/mortgage/calculate?price=224900&downpayment=44980&term=30.0&rate=3.827&tax_rate=1.2485549449920654&hoi=56.0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150"
    },
    "mortgage": {
        "loan_amount": 179920,
        "rate": 3.827,
        "term": 30,
        "monthly_payment": 1131,
        "principal_and_interest": 841,
        "monthly_property_taxes": 234,
        "monthly_home_insurance": 56,
        "hoa_fees": 0,
        "monthly_mortgage_insurance": 0,
        "total_payment": 302803,
        "down_payment": 44980
    }
}
```

This endpoint is a mortgage calculator

### HTTP Request

`GET https://realtor.p.rapidapi.com/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
hoi | double (required) | Home insurance
tax_rate | double (required) | Property tax
downpayment | int (required) | Down payment
price | int (required) | Home price
term | double (required) | Mortgage loan type
rate | double (required) | Interest rate

## finance/rates

```shell
curl "https://realtor.p.rapidapi.com/finance/rates?loc=93505" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150"
    },
    "rates": {
        "property_tax": 1.25,
        "insurance_rate": 0.3,
        "average_rate_30_year": "3.196",
        "average_rate_30_year_fha": "3.13",
        "average_rate_30_year_va": "3.061",
        "average_rate_20_year": "2.949",
        "average_rate_15_year": "2.559",
        "average_rate_10_year": "2.405",
        "average_rate_51_arm": "2.847",
        "average_rate_71_arm": "2.973",
        "meta": {
            "warnings": ""
        }
    }
}
```

This endpoint is used to get finance rates

### HTTP Request

`GET https://realtor.p.rapidapi.com/finance/rates`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
loc | string (required) | The postal code

## agents/list

```shell
curl "https://realtor.p.rapidapi.com/agents/list?offset=20&limit=20&postal_code=11234&name&types=agent&sort=recent_activity_high" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "matching_rows": 127,
    "agents": [
        {
            "address": {
                "line": "91A Lincoln Ave",
                "line2": "",
                "city": "Staten Island",
                "postal_code": "10306",
                "state_code": "NY",
                "state": "",
                "country": ""
            },
            "advertiser_id": 884288,
            "agent_rating": 0,
            "background_photo": {
                "href": "https://ap.rdcpix.com/958484605/d9d94befef2a86a373d6ff5d7d36c257g-c0s.jpg"
            },
            "broker": {
                "fulfillment_id": 3131907,
                "designations": [],
                "name": "Exit Realty Top Properties -  Broker",
                "accent_color": "",
                "photo": {
                    "href": "https://ap.rdcpix.com/1588673729/4aef38886b05339dd6b7e309a0148e65k-c0o.jpg"
                },
                "video": ""
            },
            "description": "Thomas D'Alcamo's extensive knowledge and experience provides him a unique view of the real estate market and market trends that he is able to share with his clients to help them make the best decisions for their needs and desires. \n\nA resident of Brooklyn since birth, he sells residential and commercial properties through the borough of Brooklyn.  Thomas specializes in selling single family homes, multifamily homes, condos, coops, and mixed use properties, his multi-faceted expertise is of great benefit to his clients.\n\nThomas D'Alcamo uses the latest internet technology to market and find homes at an expert level.\n\nHe is a member in good standing of the Brooklyn Board of Realtors, New York State Association of Realtors, and the National Association of Realtors in addition to the Brooklyn Multiple Listing Service.\n\nThomas helps the community by donating to local charities and donating to Habitat for Humanity.  To date EXIT Realty  has donated over 2 Million to the charity and built more than 15 Habitat Homes.\n\nHe will be there for you, to walk with and guide you through one of the most personal, emotional, and financial investments you will make in your life.",
            "designations": [],
            "first_month": 0,
            "first_name": "Thomas",
            "first_year": 2008,
            "has_photo": true,
            "href": "https://www.exittopproperties.com/agents/7-thomas-dalcamo-jr/",
            "id": "56c8442189a68901006e8643",
            "is_realtor": true,
            "languages": [],
            "last_name": "DAlcamo",
            "last_updated": "Thu, 14 Jan 2021 00:05:20 GMT",
            "marketing_area_cities": [
                {
                    "city_state": "New York_NY",
                    "name": "New York",
                    "state_code": "NY"
                },
                ...
            ],
            "mls": [
                {
                    "member": {
                        "id": "TD3521"
                    },
                    "id": 1212,
                    "abbreviation": "BONY",
                    "type": "A",
                    "primary": false
                },
                ...
            ],
            "nar_only": 1,
            "nick_name": "",
            "nrds_id": "631002336",
            "office": {
                "name": "EXIT REALTY TOP PROPERTIES",
                "mls": [
                    {
                        "member": {
                            "id": "20912"
                        },
                        "id": 604,
                        "abbreviation": "SINY",
                        "type": "O",
                        "primary": true
                    }
                ],
                "phones": [
                    {
                        "ext": "",
                        "number": "(718) 256-4000",
                        "type": "Office"
                    }
                ],
                "phone_list": {
                    "phone_1": {
                        "type": "Office",
                        "number": "7182564000",
                        "ext": ""
                    }
                },
                "photo": {
                    "href": "http://ap.rdcpix.com/4202a179bb11b2e778826acb63a1accbo-b1637540070s.jpg"
                },
                "slogan": "",
                "website": "www.exittopproperties.com",
                "video": null,
                "fulfillment_id": 3008890,
                "address": {
                    "line": "91A Lincoln Ave",
                    "line2": "",
                    "city": "Staten Island",
                    "postal_code": "10306",
                    "state_code": "NY",
                    "state": "",
                    "country": ""
                },
                "email": "tomcodal@aol.com",
                "nrds_id": null
            },
            "party_id": 2398086,
            "person_name": "Thomas D'Alcamo",
            "phones": [
                {
                    "ext": "",
                    "number": "(917) 544-9091",
                    "type": "Mobile"
                },
                {
                    "ext": "",
                    "number": "(718) 256-4000",
                    "type": "Office"
                }
            ],
            "photo": {
                "href": "https://ap.rdcpix.com/1986682203/c1712056de53c8f790ff98314a58f2b8a-e0s.jpg"
            },
            "recommendations_count": 0,
            "review_count": 0,
            "role": "agent",
            "served_areas": [
                {
                    "name": "Brooklyn",
                    "state_code": "NY"
                },
                {
                    "name": "Staten Island",
                    "state_code": "NY"
                }
            ],
            "settings": {
                "share_contacts": false,
                "full_access": false,
                "display_listings": true,
                "far_override": false,
                "show_stream": false,
                "terms_of_use": false,
                "has_dotrealtor": false,
                "display_sold_listings": true,
                "display_price_range": true,
                "display_ratings": false,
                "loaded_from_sb": false,
                "broker_data_feed_opt_out": false,
                "unsubscribe": {
                    "autorecs": false,
                    "recapprove": false,
                    "account_notify": false
                },
                "cfb_wizard_step": "account_integration",
                "new_feature_popup_closed": {
                    "agent_left_nav_avatar_to_profile": false
                },
                "profile_wizard": {
                    "realsatisfied_opt_out": false,
                    "tt_opt_out": false
                }
            },
            "slogan": "",
            "specializations": [
                {
                    "name": "Buyer's Agent"
                },
                ...
            ],
            "title": "Broker Associate",
            "types": "agent",
            "user_languages": [],
            "web_url": "https://www.realtor.com/realestateagents/Thomas-D'Alcamo_Staten-Island_NY_884288_366799863",
            "zips": [
                "11234",
                ...
            ],
            "email": "thomasdalcamo@gmail.com",
            "full_name": "Thomas D'Alcamo",
            "name": "Thomas D'Alcamo, Broker Associate",
            "agent_type": [
                "buyer",
                "seller"
            ],
            "for_sale_price": {
                "count": 9,
                "min": 115000,
                "max": 1825000,
                "last_listing_date": "2021-03-08T21:16:00Z"
            },
            "recently_sold": {
                "count": 25,
                "min": 249999,
                "max": 1010000,
                "last_sold_date": "2021-04-05"
            },
            "agent_team_details": {
                "is_team_member": false
            }
        },
        ...
    ],
    "metadata": {
        "title": "Find Realtors & Real Estate Agents in 11234 | realtor.com®",
        "description": "Find a Realtor® in 11234 on realtor.com®. 11234 Realtors® can give you a leg up in real estate.",
        "canonical_url": "https://www.realtor.com/realestateagents/11234",
        "header_1": "11234 Realtors® & Real Estate Agents",
        "deep_links": {
            "ios": "ios-app://336698281/move-rdc/www.realtor.com/realestateagents/11234",
            "android": "android-app://com.move.realtor/move-rdc/www.realtor.com/realestateagents/11234"
        }
    },
    "snippets": {
        ...
    }
}
```

This endpoint is used to list agents with options and filters

### HTTP Request

`GET https://realtor.p.rapidapi.com/agents/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | For paging purpose (max 20)
name  | string | Search for agent or team or company by name
postal_code | string | Zip code or postal code
types| string | One of the followings : agent &#124; team &#124; office
recommendations_count_min | int | Number of recommendations (max 10)
agent_rating_min | int | Rating (max 5)
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
agent_type | string | One of the followings or leave empty : buyer &#124; seller
sort | int | One of the followings : recent_activity_high &#124; recently_sold_high &#124; for_sale_count_high &#124; recommendations_count_high &#124; agent_rating_high

## properties/v2/list-sold

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/list-sold?offset=0&limit=200&city=California City&state_code=CA" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "core.3",
        "tracking_params": {
            "channel": "not_for_sale",
            "siteSection": "not_for_sale",
            "city": "California City",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "California City, CA",
            "state": "CA",
            "zip": "unknown",
            "srpPropertyStatus": "srp:not_for_sale",
            "listingActivity": "unknown",
            "propertyStatus": "not_for_sale",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "200",
            "sortResults": "sold_date",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|client_id|rdc_mobile_native,13.3.0.53|os|13.3.1|prop_status|recently_sold|schema|core.3|limit|offset|city|California+City|state_code|CA|sort|sold_date|for_sale|count|total^5K|0|5K|65^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|D|E|P|F|Q|G|H|I|J|K|L]|A|M|N|R|O|S]]",
        "returned_rows": 200,
        "matching_rows": 221
    },
    "properties": [
        {
            "property_id": "O9271317639",
            "listing_id": "2926140470",
            "prop_type": "land",
            "list_date": "2021-02-17T22:45:59Z",
            "last_update": "2021-04-07T10:53:17Z",
            "year_built": null,
            "beds": null,
            "baths_half": null,
            "prop_status": "not_for_sale",
            "address": {
                "line": "0-Poppy Lot 269",
                "street_number": null,
                "street": null,
                "street_suffix": null,
                "unit": "Lot 269",
                "city": "California City",
                "state": "California",
                "state_code": "CA",
                "postal_code": "93504"
            },
            "mls": {
                "abbreviation": "MRCA",
                "id": "DW21033328"
            },
            "client_display_flags": {
                "presentation_status": "recently_sold",
                "is_showcase": false,
                "lead_form_phone_required": false,
                "price_change": 0,
                "is_co_broke_email": false,
                "has_open_house": false,
                "is_foreclosure": false,
                "is_short_sale": false,
                "is_co_broke_phone": false,
                "is_new_listing": false,
                "is_new_plan": false,
                "is_new_construction": false,
                "is_turbo": false,
                "is_office_standard_listing": false,
                "suppress_map_pin": false,
                "show_contact_a_lender_in_lead_form": false,
                "show_veterans_united_in_lead_form": false,
                "is_showcase_choice_enabled": false,
                "is_recently_sold": true
            },
            "sold_history": [],
            "products": [
                "core.agent",
                "core.broker",
                "suppress_foreclosure"
            ],
            "office": {
                "advertiser_id": 1036104,
                "name": "CENTURY 21 Allstars",
                "email": "info@c21allstars.com",
                "href": "http://www.C21Allstars.com",
                "photo": {
                    "href": "https://ap.rdcpix.com/1780012821/43e34275cde8c350be655af95e6297c2g-c0l.jpg"
                },
                "id": "9da0332f83805464185da2ca86a1921a",
                "phones": [
                    {
                        "number": "562-863-2121",
                        "type": "office",
                        "primary": true
                    },
                    ...
                ]
            },
            "agents": [
                {
                    "primary": true,
                    "advertiser_id": "1063885",
                    "id": "1063885",
                    "photo": {
                        "href": "https://ap.rdcpix.com/2008804785/028b1417cde29ac26c1b0a394cca7ed2a-c0od-r7_w110.jpg"
                    },
                    "name": "Eduardo Bailon"
                }
            ],
            "lot_size": {
                "size": 7396,
                "units": "sqft"
            },
            "price": 7000,
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/0-Poppy-Lot-269_California-City_CA_93504_M92713-17639",
            "rdc_app_url": "move-rdc://www.realtor.com/realestateandhomes-detail/0-Poppy-Lot-269_California-City_CA_93504_M92713-17639",
            "baths": 0,
            "data_source_name": "mls",
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9271317639|list_id|2926140470|page|rank|data_source|mls|advertiser_id|agent|office|property_status|product_code|advantage_code^1|1|MSWD|M7GO|PAC|0|5^^$0|1|2|$3|4|5|6|7|H|8|I|9|A|B|$C|J|D|K]|E|L|F|M|G|N]]",
            "is_new_construction": false,
            "photo_count": 7,
            "photos": [
                {
                    "description": null,
                    "href": "https://ap.rdcpix.com/03eead593e382ee3f374fcd31c34ebb2l-m2439841187s.jpg",
                    "type": null,
                    "title": null,
                    "tags": [
                        {
                            "label": "road_view",
                            "probability": 0.9693135619163513
                        },
                        {
                            "label": "farm_land",
                            "probability": 0.030497603118419647
                        },
                        {
                            "label": "yard",
                            "probability": 0.00013851378753315657
                        }
                    ]
                },
                ...
            ]
        },
        ...
    ]
}
```

This endpoint is used to list sold properties

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/list-sold`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 200)
city | string (required) | The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)
state_code | string (required) | The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)
postal_code | string (required) | Zip code or postal code (do not use this parameter with city and state_code)
radius | int | Radius in miles to look for properties (1 to 20)
baths_min | int | Min baths of properties
beds_min | int | Min beds of properties
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
age_min | int | Min age of home
age_max | int | Max age of home
lot_sqft_max | int | Max Lot/Acreage size
lot_sqft_min | int | Min Lot/Acreage size
prop_type | string | One of the followings (separated by comma for multiple values): single_family &#124; multi_family &#124; condo &#124; mobile &#124; land &#124; farm &#124; other
sort | string | One of the followings : sold_date &#124; beds_high &#124; price_low &#124; price_high &#124; lot_sqft_high

## properties/v2/list-for-rent

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/list-for-rent?offset=0&limit=200&city=California City&state_code=CA&sort=relevance" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "core.3",
        "tracking_params": {
            "channel": "for_rent",
            "siteSection": "for_rent",
            "city": "California City",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "California City, CA",
            "state": "CA",
            "zip": "unknown",
            "srpPropertyStatus": "srp:for_rent",
            "listingActivity": "unknown",
            "propertyStatus": "for_rent",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "1",
            "sortResults": "freshest",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|client_id|rdc_mobile_native,13.3.0.53|os|13.3.1|prop_status|for_rent|schema|core.3|limit|offset|city|California+City|state_code|CA|sort|freshest|count|total^5K|0|1|1^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|D|E|O|F|P|G|H|I|J|K|L]|A|B|M|Q|N|R]]",
        "returned_rows": 1,
        "matching_rows": 1
    },
    "properties": [
        {
            "property_id": "R9649387309",
            "listing_id": "2927893241",
            "prop_type": "condo",
            "list_date": "2021-04-08T08:52:03.000Z",
            "last_update": "2021-04-08T08:52:03.000Z",
            "listing_status": "active",
            "beds": 1,
            "baths_full": 1,
            "prop_status": "for_rent",
            "address": {
                "city": "California City",
                "country": "USA",
                "county": "Kern",
                "county_needed_for_uniq": false,
                "lat": 35.12982,
                "line": "21309 Lake Shore Dr",
                "postal_code": "93505",
                "state_code": "CA",
                "state": "California",
                "time_zone": "America/Los_Angeles",
                "lon": -117.942165
            },
            "client_display_flags": {
                "presentation_status": "for_rent",
                "is_showcase": false,
                "lead_form_phone_required": true,
                "price_change": 0,
                "has_specials": false,
                "is_new_listing": true,
                "is_mls_rental": false,
                "is_rental_community": false,
                "is_rental_unit": true,
                "is_co_star": false,
                "is_apartmentlist": false,
                "suppress_map_pin": false,
                "suppress_phone_call_lead_event": false,
                "price_reduced": false
            },
            "products": [
                "_UNIT_RENTAL",
                "_UNIT_RENTAL",
                "_UNIT_RENTAL",
                "_UNIT_RENTAL",
                "_UNIT_RENTAL"
            ],
            "agents": [
                {
                    "primary": true
                }
            ],
            "lead_forms": {
                "form": {
                    "name": {
                        "required": true,
                        "minimum_character_count": 1
                    },
                    "email": {
                        "required": true,
                        "minimum_character_count": 5
                    },
                    "move_in_date": {
                        "required": false,
                        "default_date": "2021-05-01T12:00:00Z",
                        "minimum_days_from_today": 1,
                        "maximum_days_from_today": 180
                    },
                    "phone": {
                        "required": true,
                        "minimum_character_count": 10,
                        "maximum_character_count": 11
                    },
                    "message": {
                        "required": false,
                        "minimum_character_count": 0
                    },
                    "show": false
                },
                "show_agent": false,
                "show_broker": false,
                "show_provider": false,
                "show_management": false
            },
            "lot_size": {
                "size": 0,
                "units": "sqft"
            },
            "building_size": {
                "size": 468,
                "units": "sqft"
            },
            "price": 1300,
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/21309-Lake-Shore-Dr_California-City_CA_93505_M96493-87309",
            "rdc_app_url": "move-rdc://www.realtor.com/realestateandhomes-detail/21309-Lake-Shore-Dr_California-City_CA_93505_M96493-87309",
            "baths": 1,
            "data_source_name": "unit_rental",
            "source": "unit_rental",
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9649387309|list_id|2927893241|page|rank|data_source|unit_rental|property_status|product_code|advantage_code^1|1|3YA|W|0^^$0|1|2|$3|4|5|6|7|E|8|F|9|A|B|G|C|H|D|I]]",
            "photo_count": 0,
            "photos": []
        }
    ]
}
```

This endpoint is used to list properties for rent

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/list-for-rent`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 200)
city | string (required) | The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)
state_code | string (required) | The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)
postal_code | string (required) | Zip code or postal code (do not use this parameter with city and state_code)
radius | int | Radius in miles to look for properties (1 to 20)
baths_min | int | Min baths of properties
beds_min | int | Min beds of properties
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
prop_type | string | One of the followings (separated by comma for multiple values): single_family &#124; multi_family &#124; condo &#124; mobile &#124; land &#124; farm &#124; other
prop_sub_type | string | One of the followings (separated by comma for multiple values): condo &#124; cond_op &#124; townhouse &#124; co_op
sort | string | One of the followings : relevance &#124; newest &#124; price_low &#124; price_high &#124; photos &#124; open_house_date &#124; sqft_high &#124; price_reduced_date
allows_cats | boolean | false/true - Whether or not cats are allowed to live in properties
allows_dogs | boolean | false/true - Whether or not dogs are allowed to live in properties
lot_sqft_max | int | Max Lot/Acreage size
lot_sqft_min | int | Min Lot/Acreage size
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
features | string | One of the followings (separated by comma for multiple values): recreation_facilities &#124; swimming_pool &#124; washer_dryer &#124; garage_1_or_more &#124; central_air &#124; fireplace &#124; spa_or_hot_tub &#124; dishwasher &#124; community_doorman &#124; community_elevator &#124; furnished &#124; laundry_room &#124; community_no_fee &#124; community_outdoor_space &#124; pets_allowed

## properties/v2/list-for-sale

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/list-for-sale?offset=0&limit=200&city=California City&state_code=CA" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "core.3",
        "tracking_params": {
            "channel": "for_sale",
            "siteSection": "for_sale",
            "city": "California City",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "California City, CA",
            "state": "CA",
            "zip": "unknown",
            "srpPropertyStatus": "srp:for_sale",
            "listingActivity": "unknown",
            "propertyStatus": "for_sale",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "200",
            "sortResults": "relevance",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|client_id|rdc_mobile_native,13.3.0.53|prop_status|for_sale|schema|core.3|limit|offset|city|California+City|state_code|CA|sort|relevance|count|total^5K|0|5K|QB^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|M|D|N|E|F|G|H|I|J]|8|9|K|O|L|P]]",
        "returned_rows": 200,
        "matching_rows": 947
    },
    "properties": [
        {
            "property_id": "M9947934519",
            "listing_id": "2928058942",
            "products": [
                "core.agent"
            ],
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/Cooper-Dr_California-City_CA_93505_M99479-34519",
            "prop_type": "land",
            "address": {
                "city": "California City",
                "line": "Cooper Dr",
                "postal_code": "93505",
                "state_code": "CA",
                "state": "California",
                "county": "Kern",
                "fips_code": "06029",
                "county_needed_for_uniq": false,
                "time_zone": "America/Los_Angeles",
                "lat": 35.118626,
                "lon": -117.934149
            },
            "branding": {
                "listing_office": {
                    "list_item": {
                        "name": "Mamayan Realty Inc",
                        "photo": null,
                        "phone": null,
                        "slogan": null,
                        "show_realtor_logo": false,
                        "link": null,
                        "accent_color": null
                    }
                }
            },
            "prop_status": "for_sale",
            "price": 12000,
            "baths": 0,
            "beds": null,
            "agents": [
                {
                    "primary": true,
                    "advertiser_id": "2174646",
                    "id": "2174646",
                    "photo": {
                        "href": "https://p.rdcpix.com/v02/ab62e2100-c0od-r7_w110.jpg"
                    },
                    "name": "George Mamayan"
                }
            ],
            "office": {
                "id": "ef5ffc65dabcd9dcded2b8a188fe1396",
                "name": "Mamayan Realty Inc"
            },
            "last_update": "2021-04-12T18:43:45Z",
            "client_display_flags": {
                "presentation_status": "for_sale",
                "is_showcase": false,
                "lead_form_phone_required": true,
                "price_change": 0,
                "is_co_broke_email": false,
                "has_open_house": false,
                "is_co_broke_phone": false,
                "is_new_listing": true,
                "is_new_plan": false,
                "is_turbo": false,
                "is_office_standard_listing": false,
                "suppress_map_pin": false,
                "show_contact_a_lender_in_lead_form": false,
                "show_veterans_united_in_lead_form": false,
                "is_showcase_choice_enabled": false
            },
            "lead_forms": {
                "form": {
                    "name": {
                        "required": true,
                        "minimum_character_count": 1
                    },
                    "email": {
                        "required": true,
                        "minimum_character_count": 5
                    },
                    "phone": {
                        "required": true,
                        "minimum_character_count": 10,
                        "maximum_character_count": 11
                    },
                    "message": {
                        "required": false,
                        "minimum_character_count": 0
                    },
                    "show": true
                },
                "show_agent": false,
                "show_broker": false,
                "show_builder": false,
                "show_contact_a_lender": false,
                "show_veterans_united": false,
                "form_type": "classic",
                "lead_type": "co_broke",
                "is_lcm_enabled": false,
                "flip_the_market_enabled": false,
                "show_text_leads": true,
                "cashback_enabled": false,
                "smarthome_enabled": false
            },
            "photo_count": 1,
            "thumbnail": "https://ap.rdcpix.com/be12f997b61db9b3ba7eb6c66a09f2bbl-m559501126x.jpg",
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9947934519|list_id|2928058942|page|rank|list_branding|listing_agent|listing_office|advertiser_id|agent|property_status|product_code|advantage_code^1|1|0|1|1ALYU|35T|0|1^^$0|1|2|$3|4|5|6|7|H|8|I|9|$A|J|B|K]|C|$D|L]|E|M|F|N|G|O]]",
            "lot_size": {
                "size": 10019,
                "units": "sqft"
            },
            "mls": {
                "name": "GreaterAntelope",
                "id": "21003094",
                "plan_id": null,
                "abbreviation": "AVCA",
                "type": "mls"
            },
            "data_source_name": "mls"
        },
        ...
    ]
}
```

This endpoint is used to list properties for sale

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/list-for-sale`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 200)
city | string (required) | The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)
state_code | string (required) | The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)
postal_code | string (required) | Zip code or postal code (do not use this parameter with city and state_code)
radius | int | Radius in miles to look for properties (1 to 20)
baths_min | int | Min baths of properties
beds_min | int | Min beds of properties
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
age_min | int | Min age of home
age_max | int | Max age of home
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
lot_sqft_max | int | Max Lot/Acreage size
lot_sqft_min | int | Min Lot/Acreage size
prop_type | string | One of the followings (separated by comma for multiple values): single_family &#124; multi_family &#124; condo &#124; mobile &#124; land &#124; farm &#124; other
prop_sub_type | string | One of the followings (separated by comma for multiple values): condo &#124; cond_op &#124; townhouse &#124; co_op
is_matterports | boolean | true/false - 3D tours only
is_foreclosure | boolean | true/false - Foreclosures only
has_open_house | boolean | true/false - Open houses only
is_pending | boolean | true/false - Pending only
is_new_plan | boolean | true/false - Homes not yet built
is_contingent | boolean | true/false - Contingent only
is_new_construction | boolean | true/false - New construction only
features | string | One of the followings (separated by comma for multiple values): garage_2_or_more &#124; view &#124; waterfront &#124; golf_course_view &#124; swimming_pool &#124; cul_de_sac &#124; hardwood_floors &#124; basement &#124; fireplace &#124; energy_efficient &#124; disability_features &#124; dining_room &#124; washer_dryer &#124; family_room &#124; den_or_office &#124; game_room &#124; central_air &#124; central_heat &#124; forced_air &#124; single_story &#124; two_or_more_stories &#124; corner_lot &#124; water_view &#124; golf_course_lot_or_frontage &#124; hill_or_mountain_view &#124; ocean_view &#124; city_view &#124; lake_view &#124; river_view &#124; community_security_features &#124; community_swimming_pool &#124; community_boat_facilities &#124; recreation_facilities &#124; community_clubhouse &#124; community_horse_facilities &#124; community_tennis_court &#124; community_park &#124; community_golf &#124; senior_community &#124; community_spa_or_hot_tub &#124; rv_or_boat_parking &#124; horse_facilities &#124; tennis_court &#124; spa_or_hot_tub &#124; garage_1_or_more &#124; garage_3_or_more &#124; carport
sort | string | One of the followings (separated by comma for multiple values): relevance &#124; newest &#124; price_low &#124; price_high &#124; photos &#124; open_house_date &#124; sqft_high &#124; price_reduced_date

## properties/v2/list-by-mls

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/list-by-mls?offset=0&limit=10&mls_id=21003094&prop_status=for_sale" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "core.3",
        "tracking_params": {
            "channel": "for_sale",
            "siteSection": "for_sale",
            "city": "unknown",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "unknown",
            "state": "unknown",
            "zip": "unknown",
            "srpPropertyStatus": "srp:for_sale",
            "listingActivity": "unknown",
            "propertyStatus": "for_sale",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "2",
            "sortResults": "unknown",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|client_id|rdc_mobile_native,13.3.0.53|os|13.3.1|schema|core.3|limit|mls_id|21003094|prop_status|for_sale|count|total^A|2|2^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|J|D|E|F|G]|F|G|H|K|I|L]]",
        "returned_rows": 2,
        "matching_rows": 2
    },
    "properties": [
        {
            "property_id": "M9947934519",
            "listing_id": "2928058942",
            "products": [
                "core.agent"
            ],
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/Cooper-Dr_California-City_CA_93505_M99479-34519",
            "prop_type": "land",
            "address": {
                "city": "California City",
                "line": "Cooper Dr",
                "postal_code": "93505",
                "state_code": "CA",
                "state": "California",
                "county": "Kern",
                "fips_code": "06029",
                "county_needed_for_uniq": false,
                "lat": 35.118626,
                "lon": -117.934149
            },
            "branding": {
                "listing_office": {
                    "list_item": {
                        "name": "Mamayan Realty Inc",
                        "photo": null,
                        "phone": null,
                        "slogan": null,
                        "show_realtor_logo": false,
                        "link": null,
                        "accent_color": null
                    }
                }
            },
            "prop_status": "for_sale",
            "price": 12000,
            "baths": 0,
            "beds": null,
            "agents": [
                {
                    "primary": true,
                    "advertiser_id": "2174646",
                    "id": "2174646",
                    "photo": {
                        "href": "https://p.rdcpix.com/v02/ab62e2100-c0od-r7_w110.jpg"
                    },
                    "name": "George Mamayan"
                }
            ],
            "office": {
                "id": "ef5ffc65dabcd9dcded2b8a188fe1396",
                "name": "Mamayan Realty Inc"
            },
            "last_update": "2021-04-12T18:43:45Z",
            "client_display_flags": {
                "presentation_status": "for_sale",
                "is_showcase": false,
                "lead_form_phone_required": true,
                "price_change": 0,
                "is_co_broke_email": false,
                "has_open_house": false,
                "is_co_broke_phone": false,
                "is_new_listing": true,
                "is_new_plan": false,
                "is_turbo": false,
                "is_office_standard_listing": false,
                "suppress_map_pin": false,
                "show_contact_a_lender_in_lead_form": false,
                "show_veterans_united_in_lead_form": false,
                "is_showcase_choice_enabled": false
            },
            "lead_forms": {
                "form": {
                    "name": {
                        "required": true,
                        "minimum_character_count": 1
                    },
                    "email": {
                        "required": true,
                        "minimum_character_count": 5
                    },
                    "phone": {
                        "required": true,
                        "minimum_character_count": 10,
                        "maximum_character_count": 11
                    },
                    "message": {
                        "required": false,
                        "minimum_character_count": 0
                    },
                    "show": true
                },
                "show_agent": false,
                "show_broker": false,
                "show_builder": false,
                "show_contact_a_lender": false,
                "show_veterans_united": false,
                "form_type": "classic",
                "lead_type": "co_broke",
                "is_lcm_enabled": false,
                "flip_the_market_enabled": false,
                "show_text_leads": true,
                "cashback_enabled": false,
                "smarthome_enabled": false
            },
            "photo_count": 1,
            "thumbnail": "https://ap.rdcpix.com/be12f997b61db9b3ba7eb6c66a09f2bbl-m559501126x.jpg",
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9947934519|list_id|2928058942|page|rank|list_branding|listing_agent|listing_office|advertiser_id|agent|property_status|product_code|advantage_code^1|1|0|1|1ALYU|35T|0|1^^$0|1|2|$3|4|5|6|7|H|8|I|9|$A|J|B|K]|C|$D|L]|E|M|F|N|G|O]]",
            "lot_size": {
                "size": 10019,
                "units": "sqft"
            },
            "mls": {
                "name": "GreaterAntelope",
                "id": "21003094",
                "plan_id": null,
                "abbreviation": "AVCA",
                "type": "mls"
            },
            "data_source_name": "mls"
        },
        ...
    ]
}
```

This endpoint is used to list properties by mls id

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/list-by-mls`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
mls_id | string (required) | The MLS ID
prop_status | string (required) | One of the followings : for_sale &#124; for_rent &#124; recently_sold
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 10)

## properties/v2/detail

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/detail?property_id=1658306335" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "core.3",
        "tracking": "type|meta|data|resource_type|property_detail|query|client_id|rdc_mobile_native,13.3.0.53|schema|core.3|tag_version|v2^^^$0|1|2|$3|4|5|$6|7|8|9|A|B]]]",
        "returned_rows": 1,
        "matching_rows": 1,
        "tracking_params": {
            "ldpPropertyStatus": "ldp:not_for_sale",
            "pageType": "ldp",
            "leadDelivery": "unknown",
            "leadEnhancements": "unknown",
            "listingActivity": "unknown",
            "productType": "basic",
            "propertyStatus": "not_for_sale",
            "listingId": "unknown",
            "rentalDataSource": "unknown",
            "advertiserIdAgent": "2893622",
            "advertiserIdBroker": "2983847",
            "advertiserIdOffice": "3645651",
            "communityId": "unknown",
            "mprId": "1658306335",
            "listingMls": "unknown",
            "planId": "unknown",
            "subId": "unknown",
            "city": "Rancho Cucamonga",
            "neighborhood": "Alta Loma",
            "state": "CA",
            "zip": "91737",
            "listingBaths": "3",
            "listingBeds": "4",
            "listingSqFt": "3568",
            "listingEnhancements": "unknown",
            "listingPrice": "1118400",
            "photoCount": "72",
            "propertyType": "ldp:single_family",
            "version": "1.0"
        }
    },
    "properties": [
        {
            "property_id": "O1658306335",
            "prop_status": "not_for_sale",
            "prop_type": "single_family",
            "suppression_flags": [
                "suppress_open_house",
                "suppress_foreclosure"
            ],
            "buyer_agent_for_far": {
                "advertiser_id": 3999758,
                "name": "Dyllan Studer",
                "nrds_verified_id": null,
                "mls_membership": {
                    "member": {
                        "id": "CV44080",
                        "agent_system_id": "CV44080",
                        "name": "DYLLAN STUDER",
                        "abbreviation": "MRCA"
                    }
                }
            },
            "broker": {
                "advertiser_id": 2983847,
                "name": "Realty Masters & Associates",
                "phone1": {
                    "number": "9093034500",
                    "type": "broker"
                }
            },
            "year_built": 2000,
            "beds": 4,
            "description": "11160 Trails End Ct, Rancho Cucamonga, CA 91737 is a single family home built in 2000. This property was last sold for $1,125,000 in 2020 and currently has an estimated value of $1,118,400. According to the Rancho Cucamonga public records, the property at 11160 Trails End Ct, Rancho Cucamonga, CA 91737 has approximately 3568 square feet, 4 beds and 3 baths with a lot size of 0.51 acres. Nearby schools include Los Osos High School, Banyan Elementary School and Vineyard Junior High School. ",
            "baths_full": 3,
            "stories": 2,
            "schools": [
                {
                    "nces_id": "060216007259",
                    "id": "078642221",
                    "greatschools_id": "0604956",
                    "name": "Banyan Elementary School",
                    "education_levels": [
                        "elementary"
                    ],
                    "funding_type": "public",
                    "lat": 34.142577,
                    "lon": -117.566744,
                    "student_count": 615,
                    "student_teacher_ratio": 25.5,
                    "location": {
                        "city_slug_id": "Alta-Loma_CA",
                        "postal_code": "91737",
                        "state": "CA",
                        "county": "San Bernardino",
                        "city": "Alta Loma",
                        "street": "10900 Mirador Drive"
                    },
                    "phone": "(909) 484-5080",
                    "distance_in_miles": 0.7,
                    "grades": {
                        "range": {
                            "low": "K",
                            "high": "6"
                        }
                    },
                    "relevance": "assigned",
                    "ratings": {
                        "great_schools_rating": 8,
                        "parent_rating": 5
                    }
                },
                ...
            ],
            "heating": "Central",
            "cooling": "Refrigerator",
            "pool": true,
            "style": "Modern",
            "address": {
                "city": "Rancho Cucamonga",
                "line": "11160 Trails End Ct",
                "unit_value": null,
                "street_direction": null,
                "street_post_direction": null,
                "postal_code": "91737",
                "address_validation_code": "121",
                "state_code": "CA",
                "state": "California",
                "county": "San Bernardino",
                "county_needed_for_uniq": false,
                "time_zone": "America/Los_Angeles",
                "lat": 34.151592,
                "lon": -117.56178,
                "neighborhood_name": "Alta Loma",
                "neighborhoods": [
                    {
                        "name": "Alta Loma",
                        "city": "Rancho Cucamonga",
                        "state_code": "CA",
                        "level": "neighborhood",
                        "id": null
                    }
                ]
            },
            "client_display_flags": {
                "presentation_status": "not_for_sale"
            },
            "tax_history": [
                {
                    "assessment": {
                        "building": 707284,
                        "land": 379984,
                        "total": 1087268
                    },
                    "market": null,
                    "tax": 12115,
                    "year": 2020
                },
                ...
            ],
            "sold_history": [
                {
                    "date": "2020-08-21T17:00:00Z",
                    "source": "MLS #IV20127774",
                    "listing": {
                        "price": 1125000
                    }
                },
                ...
            ],
            "property_history": [
                {
                    "event_name": "Sold",
                    "date": "2020-08-21T17:00:00Z",
                    "price": 1125000,
                    "price_range_min": null,
                    "price_range_max": null,
                    "price_changed": 0,
                    "sqft": 3568,
                    "datasource_name": "CRMLS",
                    "source": "MLS #IV20127774",
                    "listing": {
                        "list_price": 1195000,
                        "last_status_change_date": "2021-02-13T18:51:02Z",
                        "last_update_date": "2020-08-21T10:53:20Z",
                        "status": "sold",
                        "list_date": "2021-02-13T18:51:02Z",
                        "listing_id": "2917884509",
                        "suppression_flags": {
                            "has_suppress_open_house": true,
                            "has_suppress_foreclosure": true
                        },
                        "photos": [
                            {
                                "href": "http://ap.rdcpix.com/be3104ee14169ec2df50c35b57f04ae3l-m4209662548s.jpg"
                            },
                            ...
                        ],
                        "description": {
                            "text": "Elegant, spacious & luxurious Deer Creek Estate home creates its own power & food! The house is ready for viewing. Solar production & Tesla backup battery, giving almost FREE energy. LOTS OF FRUIT BEARING TREES AND GARDEN. This property has it all. Stylish entertainment areas indoors and out, spectacular mountain views, pool and spa with slide and diving rocks, putting green, play area for the kids, 3 gardens, multiple fruit trees and grape vines, RV parking, huge solar system with Tesla backup batteries, beautiful kitchen with granite counter tops and island, fireplaces in master bedroom (double sided), living room and family room, large office area, exercise room, walk in closets and much much more. The master bedroom includes a double sided fireplace, ceiling fan, exercise area, beautiful Jacuzzi style tub, two walk in closets and a balcony with walkway leading to a secluded area covered by bougainvillea. You'll love entertaining by the pool with waterfalls, a 40' long grape arbor patio lined with lights & a slide. The property is richly landscaped with palms, fruit trees (lemon, lime, olive, peach, pear, avocado, apple, cherry, orange, plum, banana), blackberry and blueberry bushes, table grape vines and various other plants and trees. Located on a quiet cul de sac with an equestrian trail running across the front. Close to shopping, parks, great schools, restaurants and much more. This property truly has it all and is a must see."
                        },
                        "advertisers": [
                            {
                                "fulfillment_id": "2893622",
                                "nrds_id": null,
                                "name": "Christopher Salabaj",
                                "email": "salabaj@sbcglobal.net",
                                "href": "",
                                "slogan": "",
                                "office": {
                                    "fulfillment_id": "3645651",
                                    "name": "Realty Masters & Associates",
                                    "email": "vicentekyan@gmail.com",
                                    "href": null,
                                    "slogan": null,
                                    "out_of_community": null,
                                    "application_url": null,
                                    "mls_set": "O-MRCA-IVRMARC"
                                },
                                "broker": {
                                    "fulfillment_id": "2983847",
                                    "name": "Realty Masters & Associates -  Broker",
                                    "accent_color": "",
                                    "logo": ""
                                },
                                "type": "seller",
                                "mls_set": "A-MRCA-IVSALACHR"
                            }
                        ],
                        "buyers": [
                            {
                                "fulfillment_id": "3999758",
                                "nrds_id": null,
                                "name": "Dyllan Studer",
                                "email": "dstuder.re@gmail.com",
                                "href": null,
                                "slogan": null,
                                "type": "buyer",
                                "mls_set": "A-MRCA-CV44080",
                                "address": {
                                    "line": "",
                                    "city": "",
                                    "postal_code": "",
                                    "state_code": "",
                                    "state": null,
                                    "country": "",
                                    "coordinate": {
                                        "lat": null,
                                        "lon": null
                                    }
                                },
                                "office": {
                                    "fulfillment_id": "3645651",
                                    "name": "Realty Masters & Associates",
                                    "email": "vicentekyan@gmail.com",
                                    "href": null,
                                    "slogan": null,
                                    "hours": null,
                                    "out_of_community": null,
                                    "application_url": null,
                                    "mls_set": "O-MRCA-51548",
                                    "address": {
                                        "line": "8659 HAVEN AVE STE 100",
                                        "city": "RANCHO CUCAMONGA",
                                        "postal_code": "91730",
                                        "state_code": null,
                                        "state": "CA",
                                        "country": "USA"
                                    },
                                    "phones": [
                                        {
                                            "number": "9093034500",
                                            "type": "office",
                                            "primary": true,
                                            "trackable": null,
                                            "ext": ""
                                        }
                                    ],
                                    "county": {
                                        "name": null
                                    }
                                },
                                "phones": [
                                    {
                                        "number": "9097199955",
                                        "type": "BUSINESS_MOBILE",
                                        "primary": true,
                                        "trackable": null,
                                        "ext": ""
                                    }
                                ],
                                "broker": {
                                    "fulfillment_id": "2983847",
                                    "name": "Realty Masters & Associates -  Broker",
                                    "accent_color": "",
                                    "logo": ""
                                }
                            }
                        ],
                        "source": {
                            "id": "MRCA",
                            "agents": [
                                {
                                    "agent_id": "IVSALACHR",
                                    "agent_name": "Christopher Salabaj",
                                    "office_id": "IVRMARC",
                                    "office_name": null,
                                    "office_phone": null,
                                    "type": "seller"
                                },
                                ...
                            ]
                        }
                    },
                    "iso_date": "2020-08-21",
                    "previous_event_price": 1225000
                },
                {
                    "event_name": "Sold",
                    "date": "2000-09-22T17:00:00Z",
                    "price": 496000,
                    "price_range_min": null,
                    "price_range_max": null,
                    "price_changed": 0,
                    "sqft": 3568,
                    "datasource_name": "",
                    "source": "Public Record",
                    "listing": null,
                    "iso_date": "2000-09-22"
                }
            ],
            "public_records": [
                {
                    "prop_type": "single_family",
                    "baths": 3,
                    "baths_half": null,
                    "baths_full": 3,
                    "baths_3qtr": null,
                    "baths_1qtr": null,
                    "beds": 4,
                    "distinct_baths": 3,
                    "sqft": 3568,
                    "building_sqft": 4549,
                    "floor_1_sqft": 1770,
                    "fireplace": "Yes",
                    "exterior1": null,
                    "garage_sqft": 981,
                    "garage_spaces": null,
                    "lot_size": 22152,
                    "lot_width": null,
                    "lot_depth": null,
                    "stories": 2,
                    "year_built": 2000,
                    "year_renovated": 2000,
                    "garage": "Attached Garage",
                    "construction_quality": null,
                    "rooms": 9,
                    "units": null,
                    "heating": "Central",
                    "cooling": "Refrigerator",
                    "construction": "Wood Frame",
                    "roofing": null,
                    "pool": "Yes",
                    "style": [
                        "Modern"
                    ],
                    "view": "Good",
                    "cl_id": "538D672F833436B5DB907A41ADCB6A06",
                    "date_updated": "04/03/2021"
                }
            ],
            "products": [
                "suppress_open_house",
                "suppress_foreclosure"
            ],
            "office": {
                "name": "Realty Masters & Associates",
                "advertiser_id": 3645651,
                "href": null,
                "photo": null,
                "email": "vicentekyan@gmail.com",
                "slogan": null,
                "phones": [
                    {
                        "number": "909-303-4500",
                        "type": "office",
                        "primary": true
                    }
                ],
                "address": {
                    "city": "RANCHO CUCAMONGA",
                    "state_code": null
                },
                "mls_membership": {
                    "member": {
                        "office_system_id": "IVRMARC"
                    }
                },
                "id": "46325f189fd44a6bd5c78f82a2ac1fed"
            },
            "agents": [
                {
                    "profile_name": "Christopher Salabaj",
                    "name": "Christopher Salabaj",
                    "advertiser_id": "2893622",
                    "href": "",
                    "photo": {
                        "href": ""
                    },
                    "nrds_id": null,
                    "nrds_verified_id": null,
                    "office_name": "Realty Masters & Associates",
                    "phones": [
                        {
                            "number": "310-920-0989",
                            "type": "office",
                            "primary": true
                        }
                    ],
                    "email": "salabaj@sbcglobal.net",
                    "slogan": "",
                    "mls_memberships": {
                        "member": {
                            "agent_system_id": "IVSALACHR",
                            "name": "Christopher Salabaj",
                            "office_system_id": "IVRMARC",
                            "id": "IVSALACHR",
                            "abbreviation": "MRCA"
                        }
                    },
                    "id": "2893622",
                    "primary": true
                }
            ],
            "lot_size": {
                "size": 22150,
                "units": "sqft"
            },
            "building_size": {
                "size": 3568,
                "units": "sqft"
            },
            "price": 1118400,
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/11160-Trails-End-Ct_Rancho-Cucamonga_CA_91737_M16583-06335",
            "rdc_app_url": "move-rdc://www.realtor.com/realestateandhomes-detail/11160-Trails-End-Ct_Rancho-Cucamonga_CA_91737_M16583-06335",
            "homevalue_web_url": "https://www.realtor.com/myhome/11160-Trails-End-Ct_Rancho-Cucamonga_CA_91737_M16583-06335/homevalue",
            "baths": 3,
            "photo_count": 72,
            "buyer_office": {
                "name": "Realty Masters & Associates",
                "advertiser_id": 3645651,
                "href": null,
                "photo": null,
                "address": {
                    "city": "RANCHO CUCAMONGA",
                    "state_code": null
                },
                "slogan": null,
                "email": "vicentekyan@gmail.com",
                "phone1": {
                    "ext": "",
                    "number": "9093034500",
                    "primary": true,
                    "trackable": null,
                    "type": "office"
                },
                "mls_memberships": {
                    "member": {
                        "office_system_id": "51548"
                    }
                },
                "id": "46325f189fd44a6bd5c78f82a2ac1fed",
                "phones": []
            },
            "data_source_name": "public_records",
            "detail_tracking": "type|property|data|prop_id|1658306335|address|city|Rancho+Cucamonga|state|CA|postal|91737|neighborhood|Alta+Loma|county|San+Bernardino|price|data_source|public_records|advertiser_id|agent|office|broker|property_status|product_code|advantage_code^NYYO|1Q0QE|26503|1RYCN|4|0|0^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|D|E|F]|G|Q|H|I|J|$K|R|L|S|M|T]|N|U|O|V|P|W]]",
            "photos": [
                {
                    "href": "https://ap.rdcpix.com/e3652ff5c81f1c17d6657b9a54cf36eal-m1510296372x.jpg"
                },
                ...
            ]
        }
    ]
}
```

This endpoint is used to get property detail information

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/detail`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
property_id | string (required) | The value of property_id field returned in  .../properties/list-.... or  .../properties/v2/list-... endpoints.

## properties/v2/list-similar-homes (Deprecating)

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/list-similar-homes?property_id=1170009314" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "home": {
            "related_homes": {
                "count": 9,
                "results": [
                    {
                        "property_id": "1172655196",
                        "list_price": 239000,
                        "href": "https://www.realtor.com/realestateandhomes-detail/21021-Lodi-Pl_California-City_CA_93505_M11726-55196",
                        "flags": {
                            "is_contingent": null,
                            "is_new_construction": null,
                            "is_pending": null,
                            "is_foreclosure": null,
                            "is_new_listing": false
                        },
                        "status": "for_sale",
                        "listing_id": "2927307180",
                        "primary_photo": {
                            "href": "https://ap.rdcpix.com/aaa98168df52d6998b98b4ff0d13dacdl-m1273523273xd-w300_h300_q80.jpg"
                        },
                        "description": {
                            "baths": 2,
                            "baths_full": null,
                            "baths_half": null,
                            "beds": 3,
                            "sqft": 1408
                        },
                        "location": {
                            "address": {
                                "city": "California City",
                                "country": "usa",
                                "line": "21021 Lodi Pl"
                            }
                        }
                    },
                    ...
                ],
                "impression_token": {
                    "product": "ir_platform",
                    "type": "impression_token",
                    "api_route": "similarhomestradeoffs",
                    "module_name": "SimilarHomes",
                    "algo_name": "MLBased",
                    "algo_version": "1.0",
                    "model_name": "LightGBM",
                    "module_type": "fs-to-fs",
                    "model_version": "1.0",
                    "impression_id": "cknfnhc5dyp5401ogapvu0no3",
                    "recommendations_count": 9,
                    "client_id": "rdc-x-hestia.graphql.server"
                }
            }
        }
    }
}
```

This endpoint is used to list similar properties for sale
* This endpoint is deprecating, the official site have changed to use .../properties/v2/list.... endpoints to list similar properties.

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/list-similar-homes`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
property_id | string (required) | The value of property_id field returned in  .../properties/list-.... or  .../properties/v2/list-... endpoints.

## properties/v2/list-similar-rental-homes (Deprecating)

```shell
curl "https://realtor.p.rapidapi.com/properties/v2/list-similar-rental-homes?property_id=M2784237816&postal_code=90001" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "properties": [
        {
            "property_id": 1299029571,
            "listing_id": 2926527343,
            "ldp_url": "/realestateandhomes-detail/8034-Crockett-Blvd_Los-Angeles_CA_90001_M12990-29571",
            "full_address_display": "8034 Crockett Blvd, Los Angeles, CA 90001",
            "photo_url": "https://ar.rdcpix.com/17b43e105ebe57b3b99409775c66861cc-f2371798193xd-w480_h480_q80.jpg",
            "price_display": "$1,650",
            "beds": "1",
            "baths": "1",
            "baths_full": null,
            "baths_half": null,
            "sqft_display": "800+",
            "search_flags": {
                "is_price_reduced": false,
                "is_new_listing": false,
                "is_pending": false
            },
            "saved_resource_id": null,
            "lat": 33.96549,
            "lon": "",
            "long": null,
            "agent_id": null,
            "price_per_sqft": 2.0625,
            "sqft": 800,
            "lot_sqft": null,
            "price": 1650,
            "year_built": null,
            "beds_display": null,
            "baths_display": null,
            "address_display": null,
            "city_state_zip": null,
            "searchable_url": null,
            "list_date": null,
            "compared_price": null,
            "compared_year_built": null,
            "compared_sqft": null,
            "compared_lot_size": null,
            "prop_status": "for_rent",
            "listed_date_time": null,
            "address": "8034 Crockett Blvd",
            "city": "Los Angeles",
            "state_code": "CA",
            "state": null,
            "postal_code": "90001",
            "lot_sqft_display": null,
            "compared_price_diff": null,
            "compared_sqft_diff": null,
            "days_on_realtor": null,
            "community_name": " ",
            "lead_attributes": null,
            "community_id": null,
            "toll_free_number": null
        },
        ...
    ]
}
```

This endpoint is used to list similar properties for rent
* This endpoint is deprecating, the official have changed to use .../properties/v2/list.... endpoints to list similar properties.

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/v2/list-similar-rental-homes`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
postal_code | string (required) | The value of postal_code field returned in all list endpoints
property_id | string (required) | The value of property_id field returned in  .../properties/list-.... or  .../properties/v2/list-... endpoints.

## properties/list-sold

```shell
curl "https://realtor.p.rapidapi.com/properties/list-sold?offset=0&limit=200&city=California City&state_code=CA&sort=price_low" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "mapsearch",
        "tracking_params": {
            "channel": "not_for_sale",
            "siteSection": "not_for_sale",
            "city": "California City",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "California City, CA",
            "state": "CA",
            "zip": "unknown",
            "srpPropertyStatus": "srp:not_for_sale",
            "listingActivity": "unknown",
            "propertyStatus": "not_for_sale",
            "propertyType": "single_family,condo,mobile,multi_family,farm",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "0-1500",
            "searchLotSqft": "0-43560",
            "searchResults": "12",
            "sortResults": "price_low",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|schema|mapsearch|prop_status|not_for_sale|is_recently_sold|client_id|rdc_mobile_native,10.16.1|limit|offset|city|California+City|state_code|CA|sort|price_low|sqft_max|lot_sqft_max|age_max|prop_type|single_family,condo,mobile,multi_family,farm|count|total^5K|0|15O|XM0|K|C|C^^$0|1|2|$3|4|5|$6|7|8|9|A|-1|B|C|D|S|E|T|F|G|H|I|J|K|L|U|M|V|N|W|O|P]|8|9|Q|X|R|Y]]"
    },
    "returned_rows": 12,
    "matching_rows": 12,
    "listings": [
        {
            "property_id": "1170665580",
            "prop_type": "single_family",
            "last_update": "2020-11-21",
            "address": "20431 88th St, California City, 93505",
            "address_new": {
                "line": "20431 88th St",
                "street_number": "20431",
                "street": "88th",
                "street_suffix": "St",
                "unit": null,
                "city": "California City",
                "state": "California",
                "state_code": "CA",
                "postal_code": "93505",
                "lat": 35.118077,
                "long": -117.97098,
                "county": "Kern"
            },
            "prop_status": "recently_sold",
            "price_raw": 95000,
            "sqft_raw": 1235,
            "is_showcase": false,
            "is_new_construction": false,
            "price": "$95,000",
            "beds": 3,
            "baths": 2,
            "sqft": "1,235 sq ft",
            "lot_size": "0.24 acres",
            "photo": "https://p.rdcpix.com/v01/lcb883945-m0s.jpg",
            "short_price": "$95K",
            "baths_half": null,
            "baths_full": 2,
            "photo_count": 1,
            "sold_date": "Oct 19 2020",
            "lat": 35.118077,
            "lon": -117.97098,
            "has_leadform": false,
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|1170665580|page|rank|property_status|product_code|advantage_code^1|1|PAC|0|0^^$0|1|2|$3|4|5|A|6|B|7|C|8|D|9|E]]"
        },
        ...
    ]
}
```

This endpoint is used to list sold properties

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/list-sold`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 200)
city | string (required) | The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)
state_code | string (required) | The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)
postal_code | string (required) | Zip code or postal code (do not use this parameter with city and state_code)
radius | int | Radius in miles to look for properties (1 to 20)
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
age_min | int | Min age of home
age_max | int | Max age of home
lot_sqft_max | int | Max Lot/Acreage size
lot_sqft_min | int | Min Lot/Acreage size
prop_type | string | One of the followings (separated by comma for multiple values): single_family &#124;  condo &#124;  mobile &#124;  multi_family &#124;  farm &#124;  land
sort | string | One of the followings : sold_date &#124; beds_high &#124; price_low &#124; price_high &#124; lot_sqft_high

## properties/list-for-sale

```shell
curl "https://realtor.p.rapidapi.com/properties/list-for-sale?offset=0&limit=200&city=California City&state_code=CA&sort=relevance" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "mapsearch",
        "tracking_params": {
            "channel": "for_sale",
            "siteSection": "for_sale",
            "city": "California City",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "California City, CA",
            "state": "CA",
            "zip": "unknown",
            "srpPropertyStatus": "srp:for_sale",
            "listingActivity": "unknown",
            "propertyStatus": "for_sale",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "200",
            "sortResults": "relevance",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|schema|mapsearch|client_id|rdc_mobile_native,10.16.1|limit|offset|city|California+City|state_code|CA|sort|relevance|prop_status|for_sale|count|total^5K|0|5K|QB^^$0|1|2|$3|4|5|$6|7|8|9|A|M|B|N|C|D|E|F|G|H]|I|J|K|O|L|P]]"
    },
    "returned_rows": 200,
    "matching_rows": 947,
    "listings": [
        {
            "property_id": "9947934519",
            "is_new_construction": false,
            "listing_id": "2928058942",
            "prop_type": "land",
            "last_update": "2021-04-12T18:43:45Z",
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/Cooper-Dr_California-City_CA_93505_M99479-34519",
            "is_turbo": false,
            "address": "Cooper Dr, California City, 93505",
            "address_new": {
                "city": "California City",
                "line": "Cooper Dr",
                "postal_code": "93505",
                "state_code": "CA",
                "state": "California",
                "county": "Kern",
                "fips_code": "06029",
                "county_needed_for_uniq": false,
                "time_zone": "America/Los_Angeles",
                "lat": 35.118626,
                "lon": -117.934149
            },
            "prop_status": "for_sale",
            "price_raw": 12000,
            "sqft_raw": null,
            "list_date": "2021-04-12T23:48:52Z",
            "advertiser_id": 2174646,
            "office_name": "Mamayan Realty Inc",
            "products": [
                "core.agent"
            ],
            "is_showcase": false,
            "price": "$12,000",
            "beds": 0,
            "baths": 0,
            "sqft": "sq ft N/A",
            "lot_size": "0.23 acres",
            "mls": {
                "name": "GreaterAntelope",
                "id": "21003094",
                "plan_id": null,
                "abbreviation": "AVCA",
                "type": "mls"
            },
            "data_source_name": "mls",
            "photo": "https://ap.rdcpix.com/be12f997b61db9b3ba7eb6c66a09f2bbl-m559501126x.jpg",
            "short_price": "$12K",
            "photo_count": 1,
            "lat": 35.118626,
            "lon": -117.934149,
            "is_new_listing": true,
            "has_leadform": true,
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9947934519|list_id|2928058942|page|rank|list_branding|listing_agent|listing_office|data_source|mls|advertiser_id|agent|property_status|product_code|advantage_code^1|1|0|1|1ALYU|35T|0|1^^$0|1|2|$3|4|5|6|7|J|8|K|9|$A|L|B|M]|C|D|E|$F|N]|G|O|H|P|I|Q]]",
            "suppression_flags": [
                "suppress_sold_info",
                "suppress_foreclosure"
            ],
            "lead_forms": [
                {
                    "type": "classic",
                    "lead_type": "co_broke",
                    "form": {
                        "name": {
                            "required": true,
                            "minimum_character_count": 1
                        },
                        "email": {
                            "required": true,
                            "minimum_character_count": 5
                        },
                        "phone": {
                            "required": true,
                            "minimum_character_count": 10,
                            "maximum_character_count": 11
                        },
                        "message": {
                            "required": false,
                            "minimum_character_count": 0
                        },
                        "agents": [
                            {
                                "advertiser_id": 2174646,
                                "has_ratings": false,
                                "is_listing_agent": true
                            }
                        ],
                        "show": true
                    },
                    "is_lcm_enabled": false,
                    "show_text_leads": true,
                    "cashback_enabled": false,
                    "smarthome_enabled": false,
                    "flip_the_market_enabled": false
                }
            ]
        },
        ...
    ]
}
```

This endpoint is used to list properties for sale

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/list-for-sale`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 200)
city | string (required) | The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)
state_code | string (required) | The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)
postal_code | string (required) | Zip code or postal code (do not use this parameter with city and state_code)
radius | int | Radius in miles to look for properties (1 to 20)
baths_min | int | Min baths of properties
beds_min | int | Min beds of properties
listed_date_min | string | Date string format yyyy-MM-dd'T'HH:mm:ss'Z' , such as : 2019-08-01T16:24:40Z .The date from which the properties have been on the official site
reduced | boolean | true/false - Price reduced only
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
age_min | int | Min age of home
age_max | int | Max age of home
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
lot_sqft_max | int | Max Lot/Acreage size
lot_sqft_min | int | Min Lot/Acreage size
prop_type | string | One of the followings (separated by comma for multiple values): single_family &#124; condo &#124; mobile &#124; multi_family &#124; farm &#124; land
is_matterports | boolean | true/false - 3D tours only
is_foreclosure | boolean | true/false - Foreclosures only
is_pending | boolean | true/false - Pending only
is_contingent | boolean | true/false - Contingent only
is_new_construction | boolean | true/false - New construction only
features | string | One of the followings (separated by comma for multiple values): basement &#124; den_or_office &#124; dining_room &#124; family_room &#124; game_room &#124; washer_dryer &#124; energy_efficient_home &#124; central_air &#124; central_heat &#124; forced_air &#124; carport &#124; garage_1_or_more &#124; garage_2_or_more &#124; garage_3_or_more &#124; rv_or_boat_parking &#124; disability_features &#124; fireplace &#124; hardwood_floors &#124; horse_facilities &#124; spa_or_hot_tub &#124; swimming_pool &#124; tennis_court &#124; single_story &#124; two_or_more_stories &#124; lease_option &#124; pets_allowed &#124; corner_lot &#124; cul_de_sac &#124; golf_course_lot_or_frontage &#124; waterfront &#124; city_view &#124; golf_course_view &#124; hill_mountain &#124; lake_view &#124; ocean_view &#124; river_view &#124; water_view &#124; view &#124; community_swimming_pool &#124; community_boat_facilities &#124; community_spa_or_hot_tub &#124; community_tennis_court &#124; community_golf &#124; community_clubhouse &#124; community_security_features &#124; senior_community &#124; community_horse_facilities &#124; community_park &#124; recreation_facilities &#124; exercise_area
sort | string | One of the followings (relevance &#124; price_low &#124; price_high &#124; photos &#124; newest &#124; open_house_date &#124; sqft_high &#124; price_reduced_date)

## properties/list-for-rent

```shell
curl "https://realtor.p.rapidapi.com/properties/list-for-rent?offset=0&limit=200&city=New York City&state_code=NY&sort=completeness,photos,freshest" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "mapsearch",
        "tracking_params": {
            "channel": "for_rent",
            "siteSection": "for_rent",
            "city": "New York City",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "New York City, NY",
            "state": "NY",
            "zip": "unknown",
            "srpPropertyStatus": "srp:for_rent",
            "listingActivity": "unknown",
            "propertyStatus": "for_rent",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "200",
            "sortResults": "price_low",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|schema|mapsearch|client_id|rdc_mobile_native,10.16.1|prop_status|for_rent|limit|offset|city|New+York+City|state_code|NY|sort|price_low|count|total^5K|0|5K|K5Z^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|M|D|N|E|F|G|H|I|J]|A|B|K|O|L|P]]"
    },
    "returned_rows": 200,
    "matching_rows": 26135,
    "listings": [
        {
            "property_id": "9344110769",
            "listing_id": "2926801155",
            "prop_type": "single_family",
            "last_update": "2021-03-09T00:00:00.000Z",
            "address": "11 Greene St in SoHo, New York, 10013",
            "address_new": {
                "city": "New York",
                "country": "USA",
                "county": "New York",
                "county_needed_for_uniq": false,
                "lat": 40.720872,
                "line": "11 Greene St",
                "long": -74.003015,
                "postal_code": "10013",
                "state_code": "NY",
                "state": "New York",
                "time_zone": "America/New_York"
            },
            "prop_status": "for_rent",
            "price_raw": 0,
            "list_date": "2021-03-10T01:03:32Z",
            "is_showcase": false,
            "has_specials": false,
            "price": "Call",
            "beds": "1",
            "baths": "Call",
            "sqft": "sq ft N/A",
            "photo": "https://ap.rdcpix.com/7c48e53c5ac989a4ba88340a06661ad6l-m1602677279s.jpg",
            "short_price": "$0/mo",
            "price_reduced": false,
            "photo_count": 1,
            "products": [
                "core.agent",
                "core.broker"
            ],
            "lat": 40.720872,
            "lon": -74.003015,
            "has_leadform": true,
            "source": "mls",
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9344110769|list_id|2926801155|page|rank|list_branding|listing_agent|listing_office|advertiser_id|agent|office|property_status|product_code|advantage_code^1|1|0|1|1MWC4|17OZV|76|0|5^^$0|1|2|$3|4|5|6|7|I|8|J|9|$A|K|B|L]|C|$D|M|E|N]|F|O|G|P|H|Q]]"
        },
        ...
    ]
}
```

This endpoint is used to list properties for rent

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/list-for-rent`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request (max 200)
city | string (required) | The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)
state_code | string (required) | The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)
postal_code | string (required) | Zip code or postal code (do not use this parameter with city and state_code)
radius | int | Radius in miles to look for properties (1 to 20)
baths_min | int | Min baths of properties
beds_min | int | Min beds of properties
price_min | int | Option filter by setting min price
price_max | int | Option filter by setting max price
prop_type | string | One of the followings (separated by comma for multiple values): apartment &#124; single_family &#124; mapi_condo_townhome &#124; other
sort | string | One of the followings : completeness &#124; photos &#124; freshest &#124; price_low &#124; price_high &#124; photos &#124; newest
allows_cats | boolean | false/true - Whether or not cats are allowed to live in properties
allows_dogs | boolean | false/true - Whether or not dogs are allowed to live in properties
no_pets_allowed | boolean | true/false - Pets are allowed or not (cannot be used with allows_dogs &#124;  allows_cats)
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
mapi_community_features | string | One of the followings (separated by comma for multiple values): community_washer_dryer &#124; community_parking &#124; central_air &#124; community_pool &#124; community_gym
listed_date_min | string | Date string format yyyy-MM-dd'T'HH:mm:ss'Z' , such as : 2019-08-01T16:24:40Z .The date from which the properties have been public

## properties/list-by-mls

```shell
curl "https://realtor.p.rapidapi.com/properties/list-by-mls" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "mapsearch",
        "tracking_params": {
            "channel": "for_sale",
            "siteSection": "for_sale",
            "city": "unknown",
            "county": "unknown",
            "neighborhood": "unknown",
            "searchCityState": "unknown",
            "state": "unknown",
            "zip": "unknown",
            "srpPropertyStatus": "srp:for_sale",
            "listingActivity": "unknown",
            "propertyStatus": "for_sale",
            "propertyType": "any",
            "searchBathrooms": "any",
            "searchBedrooms": "any",
            "searchMaxPrice": "unknown",
            "searchMinPrice": "unknown",
            "searchRadius": "unknown",
            "searchHouseSqft": "any",
            "searchLotSqft": "any",
            "searchResults": "2",
            "sortResults": "price_low",
            "searchCoordinates": "unknown",
            "version": "1.0"
        },
        "tracking": "type|meta|data|resource_type|property_list|query|schema|mapsearch|client_id|rdc_mobile_native,10.16.1|limit|offset|mls_id|21003094|sort|price_low|prop_status|for_sale|count|total^5K|0|2|2^^$0|1|2|$3|4|5|$6|7|8|9|A|K|B|L|C|D|E|F]|G|H|I|M|J|N]]"
    },
    "returned_rows": 2,
    "matching_rows": 2,
    "listings": [
        {
            "property_id": "9947934519",
            "is_new_construction": false,
            "listing_id": "2928058942",
            "prop_type": "land",
            "last_update": "2021-04-12T18:43:45Z",
            "rdc_web_url": "https://www.realtor.com/realestateandhomes-detail/Cooper-Dr_California-City_CA_93505_M99479-34519",
            "is_turbo": false,
            "address": "Cooper Dr, California City, 93505",
            "address_new": {
                "city": "California City",
                "line": "Cooper Dr",
                "postal_code": "93505",
                "state_code": "CA",
                "state": "California",
                "county": "Kern",
                "fips_code": "06029",
                "county_needed_for_uniq": false,
                "lat": 35.118626,
                "lon": -117.934149
            },
            "prop_status": "for_sale",
            "price_raw": 12000,
            "sqft_raw": null,
            "list_date": "2021-04-12T23:48:52Z",
            "advertiser_id": 2174646,
            "office_name": "Mamayan Realty Inc",
            "products": [
                "core.agent"
            ],
            "is_showcase": false,
            "price": "$12,000",
            "beds": 0,
            "baths": 0,
            "sqft": "sq ft N/A",
            "lot_size": "0.23 acres",
            "mls": {
                "name": "GreaterAntelope",
                "id": "21003094",
                "plan_id": null,
                "abbreviation": "AVCA",
                "type": "mls"
            },
            "data_source_name": "mls",
            "photo": "https://ap.rdcpix.com/be12f997b61db9b3ba7eb6c66a09f2bbl-m559501126x.jpg",
            "short_price": "$12K",
            "photo_count": 1,
            "lat": 35.118626,
            "lon": -117.934149,
            "is_new_listing": true,
            "has_leadform": true,
            "page_no": 1,
            "rank": 1,
            "list_tracking": "type|property|data|prop_id|9947934519|list_id|2928058942|page|rank|list_branding|listing_agent|listing_office|data_source|mls|advertiser_id|agent|property_status|product_code|advantage_code^1|1|0|1|1ALYU|35T|0|1^^$0|1|2|$3|4|5|6|7|J|8|K|9|$A|L|B|M]|C|D|E|$F|N]|G|O|H|P|I|Q]]",
            "suppression_flags": [
                "suppress_sold_info",
                "suppress_foreclosure"
            ],
            "lead_forms": [
                {
                    "type": "classic",
                    "lead_type": "co_broke",
                    "form": {
                        "name": {
                            "required": true,
                            "minimum_character_count": 1
                        },
                        "email": {
                            "required": true,
                            "minimum_character_count": 5
                        },
                        "phone": {
                            "required": true,
                            "minimum_character_count": 10,
                            "maximum_character_count": 11
                        },
                        "message": {
                            "required": false,
                            "minimum_character_count": 0
                        },
                        "agents": [
                            {
                                "advertiser_id": 2174646,
                                "has_ratings": false,
                                "is_listing_agent": true
                            }
                        ],
                        "show": true
                    },
                    "is_lcm_enabled": false,
                    "show_text_leads": true,
                    "cashback_enabled": false,
                    "smarthome_enabled": false,
                    "flip_the_market_enabled": false
                }
            ]
        },
        ...
    ]
}
```

This endpoint is used to list properties by MLS ID

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/list-by-mls`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
mls_id | string (required) | The MLS ID
offset | int | The offset of items to be ignored in response for paging
limit | int | The number of items to be responded in every request
sort | string | One of the followings : price_low &#124; price_high &#124; photos &#124; newest &#124; open_house_date

## properties/list-similarities

```shell
curl "https://realtor.p.rapidapi.com/properties/list-similarities?property_id=1658306335&limit=12&prop_status=for_sale" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150"
    },
    "results": {
        "similar_homes": {
            "total": 9,
            "count": 9,
            "properties": [
                {
                    "property_id": "1492100231",
                    "listing_id": "2927985367",
                    "last_sold_price": 204000,
                    "list_price_min": null,
                    "list_price_max": null,
                    "list_price": 850000,
                    "href": "https://www.realtor.com/realestateandhomes-detail/6022-Klusman-Ave_Rancho-Cucamonga_CA_91737_M14921-00231",
                    "permalink": "6022-Klusman-Ave_Rancho-Cucamonga_CA_91737_M14921-00231",
                    "list_date": "2021-04-10T00:50:22Z",
                    "last_update_date": "2021-04-09T17:44:00Z",
                    "status": "for_sale",
                    "description": {
                        "beds_min": null,
                        "beds_max": null,
                        "beds": 4,
                        "baths_min": null,
                        "baths_max": null,
                        "baths": 3,
                        "baths_full": 2,
                        "baths_half": 1,
                        "garage": 3,
                        "sqft_min": null,
                        "sqft_max": null,
                        "sqft": 2393,
                        "lot_sqft": 19889,
                        "type": "single_family",
                        "sub_type": null,
                        "year_built": 1981,
                        "sold_price": 204000
                    },
                    "location": {
                        "address": {
                            "line": "6022 Klusman Ave",
                            "street_number": "6022",
                            "street_name": "Klusman",
                            "street_suffix": "Ave",
                            "unit": null,
                            "city": "Alta Loma",
                            "state_code": "CA",
                            "postal_code": "91737",
                            "country": "USA",
                            "state": "California",
                            "coordinate": {
                                "lat": 34.144628,
                                "lon": -117.596074
                            }
                        }
                    },
                    "flags": {
                        "is_contingent": null,
                        "is_garage_present": true,
                        "is_new_construction": null,
                        "is_pending": null,
                        "is_short_sale": null,
                        "is_foreclosure": null,
                        "is_senior_community": null,
                        "is_for_rent": null,
                        "is_deal_available": null,
                        "is_price_excludes_land": null,
                        "is_subdivision": null,
                        "is_plan": null
                    },
                    "photos": [
                        {
                            "href": "https://ap.rdcpix.com/285dd747a7dad42c40dcff27ec015878l-m3796513023s.jpg"
                        },
                        ...
                    ],
                    "primary_photo": {
                        "href": "https://ap.rdcpix.com/285dd747a7dad42c40dcff27ec015878l-m3796513023s.jpg"
                    },
                    "additional_info": {
                        "compared_price": "24% less expensive",
                        "compared_price_diff": 275000,
                        "price_display": "$850,000",
                        "beds_display": "4 bd",
                        "baths_display": "3 ba",
                        "sqft_display": "2,393 sq ft",
                        "compared_sqft": "1,175 sq ft smaller",
                        "compared_sqft_diff": 1175,
                        "compared_lot_size": "Smaller lot",
                        "compared_year_built": "19 years older",
                        "photo_url": "https://ap.rdcpix.com/285dd747a7dad42c40dcff27ec015878l-m3796513023xd-w300_h300_q80.jpg"
                    }
                },
                ...
            ]
        }
    }
}
```

This endpoint is used to list similar properties

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/list-similarities`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
property_id | string (required) | The value of property_id field returned in  .../properties/list-.... or  .../properties/v2/list-... endpoints.
prop_status | string (required) | One of the followings : for_sale &#124; for_rent
limit | int | The number of items responded 

## properties/detail

```shell
curl "https://realtor.p.rapidapi.com/properties/detail?property_id=1658306335&prop_status=recently_sold" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150",
        "schema": "legacy",
        "tracking": "type|meta|data|resource_type|property_detail|query|schema|legacy|client_id|rdc_mobile_native,10.16.1|tag_version|v2|prop_status|for_sale^^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|D]]]",
        "tracking_params": {
            "ldpPropertyStatus": "ldp:not_for_sale",
            "pageType": "ldp",
            "leadDelivery": "unknown",
            "leadEnhancements": "unknown",
            "listingActivity": "unknown",
            "productType": "basic",
            "propertyStatus": "not_for_sale",
            "listingId": "unknown",
            "rentalDataSource": "unknown",
            "advertiserIdAgent": "2893622",
            "advertiserIdBroker": "2983847",
            "advertiserIdOffice": "3645651",
            "communityId": "unknown",
            "mprId": "1658306335",
            "listingMls": "unknown",
            "planId": "unknown",
            "subId": "unknown",
            "city": "Rancho Cucamonga",
            "neighborhood": "Alta Loma",
            "state": "CA",
            "zip": "91737",
            "listingBaths": "3",
            "listingBeds": "4",
            "listingSqFt": "3568",
            "listingEnhancements": "unknown",
            "listingPrice": "1118400",
            "photoCount": "72",
            "propertyType": "ldp:single_family",
            "version": "1.0"
        }
    },
    "listing": {
        "prop_type": "single_family",
        "data_source_name": "public_records",
        "price": 1118400,
        "year_built": 2000,
        "permalink": "11160-Trails-End-Ct_Rancho-Cucamonga_CA_91737_M16583-06335",
        "suppression_flags": [
            "suppress_open_house",
            "suppress_foreclosure"
        ],
        "address": {
            "city": "Rancho Cucamonga",
            "line": "11160 Trails End Ct",
            "unit_value": null,
            "street_direction": null,
            "street_post_direction": null,
            "postal_code": "91737",
            "address_validation_code": "121",
            "state_code": "CA",
            "state": "California",
            "county": "San Bernardino",
            "county_needed_for_uniq": false,
            "time_zone": "America/Los_Angeles",
            "lat": 34.151592,
            "neighborhood_name": "Alta Loma",
            "neighborhoods": [
                {
                    "name": "Alta Loma",
                    "city": "Rancho Cucamonga",
                    "state_code": "CA",
                    "level": "neighborhood",
                    "id": null
                }
            ],
            "long": -117.56178
        },
        "beds": 4,
        "baths_full": 3,
        "baths": 3,
        "sqft": 3568,
        "lot_sqft": 22150,
        "price_history": [
            {
                "date": "2020-08-21T17:00:00Z",
                "price": 1125000
            }
        ],
        "tax_history": [
            {
                "assessment": {
                    "building": 707284,
                    "land": 379984,
                    "total": 1087268
                },
                "market": null,
                "tax": 12115,
                "year": 2020
            },
            ...
        ],
        "property_history": [
            {
                "event_name": "Sold",
                "date": "2020-08-21T17:00:00Z",
                "price": 1125000,
                "price_range_min": null,
                "price_range_max": null,
                "price_changed": 0,
                "sqft": 3568,
                "datasource_name": "CRMLS",
                "source": "MLS #IV20127774",
                "listing": {
                    "list_price": 1195000,
                    "last_status_change_date": "2021-02-13T18:51:02Z",
                    "last_update_date": "2020-08-21T10:53:20Z",
                    "status": "sold",
                    "list_date": "2021-02-13T18:51:02Z",
                    "listing_id": "2917884509",
                    "suppression_flags": {
                        "has_suppress_open_house": true,
                        "has_suppress_foreclosure": true
                    },
                    "photos": [
                        {
                            "href": "http://ap.rdcpix.com/be3104ee14169ec2df50c35b57f04ae3l-m4209662548s.jpg"
                        },
                        ...
                    ],
                    "description": {
                        "text": "Elegant, spacious & luxurious Deer Creek Estate home creates its own power & food! The house is ready for viewing. Solar production & Tesla backup battery, giving almost FREE energy. LOTS OF FRUIT BEARING TREES AND GARDEN. This property has it all. Stylish entertainment areas indoors and out, spectacular mountain views, pool and spa with slide and diving rocks, putting green, play area for the kids, 3 gardens, multiple fruit trees and grape vines, RV parking, huge solar system with Tesla backup batteries, beautiful kitchen with granite counter tops and island, fireplaces in master bedroom (double sided), living room and family room, large office area, exercise room, walk in closets and much much more. The master bedroom includes a double sided fireplace, ceiling fan, exercise area, beautiful Jacuzzi style tub, two walk in closets and a balcony with walkway leading to a secluded area covered by bougainvillea. You'll love entertaining by the pool with waterfalls, a 40' long grape arbor patio lined with lights & a slide. The property is richly landscaped with palms, fruit trees (lemon, lime, olive, peach, pear, avocado, apple, cherry, orange, plum, banana), blackberry and blueberry bushes, table grape vines and various other plants and trees. Located on a quiet cul de sac with an equestrian trail running across the front. Close to shopping, parks, great schools, restaurants and much more. This property truly has it all and is a must see."
                    },
                    "advertisers": [
                        {
                            "fulfillment_id": "2893622",
                            "nrds_id": null,
                            "name": "Christopher Salabaj",
                            "email": "salabaj@sbcglobal.net",
                            "href": "",
                            "slogan": "",
                            "office": {
                                "fulfillment_id": "3645651",
                                "name": "Realty Masters & Associates",
                                "email": "vicentekyan@gmail.com",
                                "href": null,
                                "slogan": null,
                                "out_of_community": null,
                                "application_url": null,
                                "mls_set": "O-MRCA-IVRMARC"
                            },
                            "broker": {
                                "fulfillment_id": "2983847",
                                "name": "Realty Masters & Associates -  Broker",
                                "accent_color": "",
                                "logo": ""
                            },
                            "type": "seller",
                            "mls_set": "A-MRCA-IVSALACHR"
                        }
                    ],
                    "buyers": [
                        {
                            "fulfillment_id": "3999758",
                            "nrds_id": null,
                            "name": "Dyllan Studer",
                            "email": "dstuder.re@gmail.com",
                            "href": null,
                            "slogan": null,
                            "type": "buyer",
                            "mls_set": "A-MRCA-CV44080",
                            "address": {
                                "line": "",
                                "city": "",
                                "postal_code": "",
                                "state_code": "",
                                "state": null,
                                "country": "",
                                "coordinate": {
                                    "lat": null,
                                    "lon": null
                                }
                            },
                            "office": {
                                "fulfillment_id": "3645651",
                                "name": "Realty Masters & Associates",
                                "email": "vicentekyan@gmail.com",
                                "href": null,
                                "slogan": null,
                                "hours": null,
                                "out_of_community": null,
                                "application_url": null,
                                "mls_set": "O-MRCA-51548",
                                "address": {
                                    "line": "8659 HAVEN AVE STE 100",
                                    "city": "RANCHO CUCAMONGA",
                                    "postal_code": "91730",
                                    "state_code": null,
                                    "state": "CA",
                                    "country": "USA"
                                },
                                "phones": [
                                    {
                                        "number": "9093034500",
                                        "type": "office",
                                        "primary": true,
                                        "trackable": null,
                                        "ext": ""
                                    }
                                ],
                                "county": {
                                    "name": null
                                }
                            },
                            "phones": [
                                {
                                    "number": "9097199955",
                                    "type": "BUSINESS_MOBILE",
                                    "primary": true,
                                    "trackable": null,
                                    "ext": ""
                                }
                            ],
                            "broker": {
                                "fulfillment_id": "2983847",
                                "name": "Realty Masters & Associates -  Broker",
                                "accent_color": "",
                                "logo": ""
                            }
                        }
                    ],
                    "source": {
                        "id": "MRCA",
                        "agents": [
                            {
                                "agent_id": "IVSALACHR",
                                "agent_name": "Christopher Salabaj",
                                "office_id": "IVRMARC",
                                "office_name": null,
                                "office_phone": null,
                                "type": "seller"
                            },
                            ..
                        ]
                    }
                },
                "iso_date": "2020-08-21",
                "previous_event_price": 1225000
            },
            {
                "event_name": "Sold",
                "date": "2000-09-22T17:00:00Z",
                "price": 496000,
                "price_range_min": null,
                "price_range_max": null,
                "price_changed": 0,
                "sqft": 3568,
                "datasource_name": "",
                "source": "Public Record",
                "listing": null,
                "iso_date": "2000-09-22"
            }
        ],
        "neighborhood": "Alta Loma",
        "neighborhoods": [
            {
                "name": "Alta Loma",
                "city": "Rancho Cucamonga",
                "state_code": "CA",
                "level": "neighborhood",
                "id": null
            }
        ],
        "raw_prop_type": "Single Family Home",
        "photo_count": 72,
        "photos": [
            {
                "href": "https://ap.rdcpix.com/e3652ff5c81f1c17d6657b9a54cf36eal-m1510296372x.jpg"
            },
            ...
        ],
        "photo": {
            "href": "https://ap.rdcpix.com/e3652ff5c81f1c17d6657b9a54cf36eal-m1510296372x.jpg"
        },
        "products": [
            "suppress_open_house",
            "suppress_foreclosure"
        ],
        "office": {
            "name": "Realty Masters & Associates",
            "advertiser_id": 3645651,
            "email": "vicentekyan@gmail.com",
            "address": {
                "city": "RANCHO CUCAMONGA"
            },
            "mls_memberships": {
                "member": {
                    "office_system_id": "IVRMARC"
                }
            },
            "phone1": {
                "number": "9093034500",
                "type": "office",
                "primary": true
            }
        },
        "heating": "Central",
        "cooling": "Refrigerator",
        "pool": true,
        "style": "Modern",
        "buyer_office": {
            "name": "Realty Masters & Associates",
            "advertiser_id": 3645651,
            "address": {
                "city": "RANCHO CUCAMONGA"
            },
            "email": "vicentekyan@gmail.com",
            "phone1": {
                "number": "9093034500",
                "primary": true,
                "type": "office"
            },
            "mls_memberships": {
                "member": {
                    "office_system_id": "51548"
                }
            }
        },
        "buyer_agent_for_far": {
            "advertiser_id": 3999758,
            "name": "Dyllan Studer",
            "mls_membership": {
                "member": {
                    "id": "CV44080",
                    "agent_system_id": "CV44080",
                    "name": "DYLLAN STUDER",
                    "abbreviation": "MRCA"
                }
            }
        },
        "agent": {
            "profile_name": "Christopher Salabaj",
            "name": "Christopher Salabaj",
            "advertiser_id": 2893622,
            "office_name": "Realty Masters & Associates",
            "email": "salabaj@sbcglobal.net",
            "mls_memberships": {
                "member": {
                    "agent_system_id": "IVSALACHR",
                    "name": "Christopher Salabaj",
                    "office_system_id": "IVRMARC",
                    "id": "IVSALACHR",
                    "abbreviation": "MRCA"
                }
            },
            "phone1": {
                "number": "3109200989",
                "type": "office",
                "primary": true
            }
        },
        "broker": {
            "advertiser_id": 2983847,
            "name": "Realty Masters & Associates",
            "phone1": {
                "number": "9093034500",
                "type": "broker"
            }
        },
        "web_url": "https://www.realtor.com/realestateandhomes-detail/11160-Trails-End-Ct_Rancho-Cucamonga_CA_91737_M16583-06335",
        "homevalue_web_url": "https://www.realtor.com/myhome/11160-Trails-End-Ct_Rancho-Cucamonga_CA_91737_M16583-06335/homevalue",
        "prop_status": "not_for_sale",
        "property_id": "1658306335",
        "reduced": false,
        "description": "11160 Trails End Ct, Rancho Cucamonga, CA 91737 is a single family home built in 2000. This property was last sold for $1,125,000 in 2020 and currently has an estimated value of $1,118,400. According to the Rancho Cucamonga public records, the property at 11160 Trails End Ct, Rancho Cucamonga, CA 91737 has approximately 3568 square feet, 4 beds and 3 baths with a lot size of 0.51 acres. Nearby schools include Los Osos High School, Banyan Elementary School and Vineyard Junior High School. ",
        "advertiser_type": "agent",
        "stories": 2,
        "client_display_flags": {
            "presentation_status": "not_for_sale"
        },
        "client_display_text": {
            "address_with_neighborhood": "11160 Trails End Ct in Alta Loma, Rancho Cucamonga, CA 91737",
            "prop_type_display_name": "Single Family Home",
            "listing_date_name": "Time on realtor.com:"
        },
        "client_provider_data": [
            {
                "item": "Listing Agent",
                "text": "Christopher Salabaj"
            },
            {
                "item": "Listing By",
                "text": "Realty Masters & Associates\n9093034500",
                "lines": [
                    {
                        "text": "Realty Masters & Associates"
                    },
                    {
                        "text": "9093034500",
                        "type": "PHONE",
                        "value": "9093034500"
                    }
                ]
            },
            {
                "item": "Broker",
                "text": "Realty Masters & Associates"
            }
        ],
        "detail_tracking": "type|property|data|prop_id|1658306335|address|city|Rancho+Cucamonga|state|CA|postal|91737|neighborhood|Alta+Loma|county|San+Bernardino|price|data_source|public_records|advertiser_id|agent|office|broker|property_status|product_code|advantage_code^NYYO|1Q0QE|26503|1RYCN|4|0|0^^$0|1|2|$3|4|5|$6|7|8|9|A|B|C|D|E|F]|G|Q|H|I|J|$K|R|L|S|M|T]|N|U|O|V|P|W]]"
    }
}
```

This endpoint is used to ...

### HTTP Request

`GET https://realtor.p.rapidapi.com/properties/detail`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
prop_status | string (required) | One of the followings : for_sale &#124; for_rent
property_id | string (required) | The value of property_id field returned in  .../properties/list-.... or  .../properties/v2/list-... endpoints.
listing_id | string | The value of listing_id field returned in  .../properties/list-.... or  .../properties/v2/list-... endpoints.


## schools/list-nearby

```shell
curl "https://realtor.p.rapidapi.com/schools/list-nearby?lat=35.129431&lon=-117.937021" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "meta": {
        "build": "3.23.150"
    },
    "schools": [
        {
            "nces_id": "062523003773",
            "id": "078590231",
            "greatschools_id": "0601317",
            "name": "Robert P. Ulrich Elementary School",
            "education_levels": [
                "elementary"
            ],
            "funding_type": "public",
            "lat": 35.122802,
            "lon": -117.967056,
            "student_count": 527,
            "student_teacher_ratio": 22.4,
            "location": {
                "city_slug_id": "California-City_CA",
                "postal_code": "93505",
                "state": "CA",
                "county": "Kern",
                "city": "California City",
                "street": "9124 Catalpa Avenue"
            },
            "phone": "(760) 373-4824",
            "distance_in_miles": 1.8,
            "grades": {
                "range": {
                    "low": "K",
                    "high": "2"
                }
            },
            "relevance": "assigned",
            "ratings": {
                "great_schools_rating": null,
                "parent_rating": 3
            },
            "district": {
                "id": "06151431811",
                "name": "Mojave Unified"
            },
            "boundary_trimmed": {
                "type": "MultiPolygon",
                "coordinates": [
                    [
                        [
                            [
                                -117.7147724,
                                35.2729929
                            ],
                            ...
                        ]
                    ]
                ]
            }
        },
        {
            "nces_id": "A0101369",
            "id": "078787551",
            "greatschools_id": "0615130",
            "name": "Western Education Center",
            "education_levels": [
                "elementary",
                "middle",
                "high"
            ],
            "funding_type": "private",
            "lat": 35.125526,
            "lon": -117.965197,
            "student_count": 10,
            "location": {
                "city_slug_id": "California-City_CA",
                "postal_code": "93505",
                "state": "CA",
                "county": "Kern",
                "city": "California City",
                "street": "9100 California City Boulevard"
            },
            "phone": "(760) 373-9112",
            "distance_in_miles": 1.6,
            "grades": {
                "range": {
                    "low": "5",
                    "high": "12"
                }
            },
            "relevance": "nearby",
            "ratings": {
                "great_schools_rating": null,
                "parent_rating": null
            },
            "district": {
                "id": "06151428551"
            }
        }
    ],
    "districts": []
}
```

This endpoint is used to list schools being near the property

### HTTP Request

`GET https://realtor.p.rapidapi.com/schools/list-nearby`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
lon | double (required) | The longitude co-ordinate
lat | double (required) | The latitude co-ordinate

# Realtor CA API

## locations/auto-complete

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/locations/auto-complete?Area=Quebec&CultureId=1" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - Success - OK",
        "Status": "Via-Cache:False",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17782"
    },
    "SubArea": [
        {
            "Location": "Quebec City, QC, Canada",
            "Longitude": "-71.2079809",
            "Latitude": "46.8138783",
            "Height": 0.25113899999999489,
            "Width": 0.415504999999996,
            "InternalResult": "False",
            "Viewport": {
                "NorthEast": {
                    "Latitude": "46.9819379",
                    "Longitude": "-71.13394"
                },
                "SouthWest": {
                    "Latitude": "46.7307989",
                    "Longitude": "-71.549445"
                }
            },
            "GEOId": "g30_f2m68c6b",
            "Polygons": []
        }
    ]
}
```

This endpoint is used to get auto complete suggestions by city, ward, street name

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/locations/auto-complete`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
Area | string (required) | City, ward, street name
CultureId | int | 1 - English &#124; 2 - French



## properties/list-commercial

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/properties/list-commercial?CultureId=1&LatitudeMax=81.14747595814636&LongitudeMax=-10.267941690981388&LatitudeMin=-22.26872153207163&LongitudeMin=-136.83037765324116&TransactionTypeId=2&PriceMin=0&BedRange=0-0&BathRange=0-0&OpenHouse=false&NumberOfDays=0&RecordsPerPage=50&CurrentPage=1&SortBy=1&SortOrder=D" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - OK",
        "Status": "Pins-Via-Cache:false;Sidebar-Items-Via-Cache:0;",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17782"
    },
    "Paging": {
        "RecordsPerPage": 50,
        "CurrentPage": 1,
        "TotalRecords": 49419,
        "MaxRecords": 500,
        "TotalPages": 10,
        "RecordsShowing": 500,
        "Pins": 435
    },
    "Results": [
        {
            "Id": "21934857",
            "MlsNumber": "1214731",
            "PublicRemarks": "Located in a central commercial zone on Burnwood Drive, this property is ready to be leased or owned. This building has approximately 10,000 square feet of space in total. The owner is willing to sell the building whole or will subdivide into individual units of typically 2000 square feet per unit. The building and or individual units is also available for lease. Financing is available for the whole building or for the individual units. (23149588)",
            "Building": {
                "SizeInterior": "10000 sqft",
                "Type": "Retail"
            },
            "Individual": [
                {
                    "IndividualID": 1944382,
                    "Name": "WAYNE SHEPPARD",
                    "Organization": {
                        "OrganizationID": 104938,
                        "Name": "RE/MAX Realty Professionals Ltd. - Goose Bay",
                        "Logo": "https://cdn.realtor.ca/organization/en-CA/TS637429401840000000/lowres/default/remaxoa.gif",
                        "Address": {
                            "AddressText": "P.O. Box 776, Station C|Happy Valley - Goose Bay, Newfoundland & Labrador A0P1C0",
                            "PermitShowAddress": true,
                            "DisseminationArea": null
                        },
                        "Phones": [
                            {
                                "PhoneType": "Telephone",
                                "PhoneNumber": "896-9234",
                                "AreaCode": "709",
                                "PhoneTypeId": "1"
                            },
                            ...
                        ],
                        "OrganizationType": "Firm",
                        "Designation": "Brokerage",
                        "PermitFreetextEmail": true,
                        "PermitShowListingLink": true,
                        "RelativeDetailsURL": "/office/firm/104938/remax-realty-professionals-ltd-goose-bay-po-box-776-station-c-happy-valley-goose-bay-newfoundland-labrador-a0p1c0",
                        "PhotoLastupdate": "2020-12-07 12:16:24 PM"
                    },
                    "Phones": [
                        {
                            "PhoneType": "Telephone",
                            "PhoneNumber": "896-9234",
                            "AreaCode": "709",
                            "PhoneTypeId": "1"
                        },
                        ...
                    ],
                    "Emails": [
                        {
                            "ContactId": "452275500"
                        }
                    ],
                    "PermitFreetextEmail": true,
                    "FirstName": "WAYNE",
                    "LastName": "SHEPPARD",
                    "CorporationDisplayTypeId": "0",
                    "PermitShowListingLink": true,
                    "RelativeDetailsURL": "/agent/1944382/wayne-sheppard-po-box-776-station-c-happy-valley---goose-bay-newfoundland-labrador-a0p1c0",
                    "RankMyAgentKey": "",
                    "RealSatisfiedKey": ""
                }
            ],
            "Property": {
                "Price": "$123,456,789",
                "Type": "Retail",
                "Address": {
                    "AddressText": "19-21 Burnwood Drive|Happy Valley - Goose Bay, Newfoundland & Labrador A0P1C0",
                    "Longitude": "-60.384115",
                    "Latitude": "53.308552",
                    "PermitShowAddress": true,
                    "DisseminationArea": null
                },
                "Photo": [
                    {
                        "SequenceId": "1",
                        "HighResPath": "https://cdn.realtor.ca/listings/TS637269670394830000/reb117/highres/1/1214731_1.jpg",
                        "MedResPath": "https://cdn.realtor.ca/listings/TS637269670394830000/reb117/medres/1/1214731_1.jpg",
                        "LowResPath": "https://cdn.realtor.ca/listings/TS637269670394830000/reb117/lowres/1/1214731_1.jpg",
                        "LastUpdated": "2020-06-05 3:17:19 PM"
                    }
                ],
                "TypeId": "305",
                "OwnershipType": "Freehold",
                "ConvertedPrice": "$123,456,789 ",
                "OwnershipTypeGroupIds": [
                    1
                ],
                "PriceUnformattedValue": "123456789"
            },
            "Business": {
                "BusinessSubType": "Restaurant, Furniture/household, Specialty retail, Sales/service",
                "BusinessType": "Restaurant (Restaurant), Retail and Wholesale (Furniture/household), Retail and Wholesale (Specialty retail), Retail and Wholesale (Sales/service)"
            },
            "Land": {
                "SizeTotal": "1/2 acre|10,890 - 21,799 sqft (1/4 - 1/2 ac)"
            },
            "PostalCode": "A0P1C0",
            "RelativeDetailsURL": "/real-estate/21934857/19-21-burnwood-drive-happy-valley-goose-bay",
            "StatusId": "1",
            "PhotoChangeDateUTC": "2020-06-05 7:17:19 PM",
            "Distance": "",
            "RelativeURLEn": "/real-estate/21934857/19-21-burnwood-drive-happy-valley-goose-bay",
            "RelativeURLFr": "/immobilier/21934857/19-21-burnwood-drive-happy-valley-goose-bay"
        }...
    ],
    "Pins": [
        {
            "key": "L1|24|-110",
            "propertyId": "",
            "count": 1,
            "longitude": "-110",
            "latitude": "24"
        },
        ...
    ],
    "GroupingLevel": "1"
}
```

This endpoint is used to list commercial properties both for lease and for sale

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/properties/list-commercial`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
LongitudeMin | double (required) | South West longitude
LatitudeMin | double (required) | South West latitude
LongitudeMax | double (required) | North East longitude
LatitudeMax | double (required) | North East latitude
CurrentPage | int | The current page on which items are displayed 
RecordsPerPage | int | Number items returned per request, max 50
BuildingSizeRange | string | 0-5000:0-5,000 sqft &#124; 5001-10000:5,001-10,000 sqft &#124; 10001-15000:10,001-15,000 sqft &#124; 250001-0:Over 250,000 sqft
BedRange | string | 0-0:Any &#124; 1-1:1 &#124; 1-0:1+ &#124; 2-2:2 &#124; 2-0:2+ &#124; 3-3:3 &#124; 3-0:3+ &#124; 4-4:4 &#124; 4-0:4+ &#124; 5-5:5 &#124; 5-0:5+
BathRange | string | 0-0:Any &#124; 1-1:1 &#124; 1-0:1+ &#124; 2-2:2 &#124; 2-0:2+ &#124; 3-3:3 &#124; 3-0:3+ &#124; 4-4:4 &#124; 4-0:4+ &#124; 5-5:5 &#124; 5-0:5+
UnitRange | string | 0-0:Any &#124; 1-1:1 &#124; 1-0:1+ &#124; 2-2:2 &#124; 2-0:2+ &#124; 3-3:3 &#124; 3-0:3+ &#124; 4-4:4 &#124; 4-0:4+ &#124; 5-5:5 &#124; 5-0:5+ &#124; .... &#124; 9-0:9+
LandSizeRange | string | 0-0:Any &#124; 1-0:1+ acres &#124; 2-0:2+ acres &#124; 5-0:5+ acres &#124; 10-0:10+ acres &#124; 50-0:50+ acres &#124; 100-0:100+ acres &#124; 200-0:200+ acres &#124; 300-0:300+ acres &#124; 400-0:400+ acres &#124; 500-0:500+ acres &#124; 1000-0:1000+ acres
SortBy | int | 1-Price($) &#124; 6-Date &#124; 11-Virtual Tour &#124; 12-Open Houses &#124; 13-More Photos
SortOrder | string | A - ascending &#124; D - descending
NumberOfDays | int | Listed since
Keywords | string | Get suitable values from .../keywords/list endpoint, separated by comma for multiple keywords, Ex : Inlaw suite,Income suite
BuildingTypeId | int | 0-No Preference &#124; 1-House &#124; 2-Duplex &#124; 3-Triplex &#124; 5-Residential Commercial Mix &#124; 6-Mobile Home &#124; 12-Special Purpose &#124; 14-Other &#124; 16-Row / Townhouse &#124; 17-Apartment &#124; 19-Fourplex &#124; 20-Garden Home &#124; 26-Modular &#124; 27-Manufactured Home/Mobile &#124; 28-Commercial Apartment &#124; 29-Manufactured Home
OpenHouseStartDate | string | Format date as MM/dd/yyyy, ex : 03/20/2020
OpenHouseEndDate | string | Format date as MM/dd/yyyy, ex : 03/31/2020
OpenHouse | boolean | false/true - Need to use together with OpenHouseStartDate and OpenHouseEndDate parameters
CultureId | int | 1 - English &#124; 2 - French
FarmTypeId | int | 0-No Preference &#124; 1-Animal &#124; 2-Boarding &#124; 3-Cash Crop &#124; 4-Feed Lot &#124; 5-Nursery &#124; 6-Market Gardening &#124; 7-Hobby Farm &#124; 8-Vineyard &#124; 9-Orchard &#124; 10-Greenhouse &#124; 12-Mixed
PriceMin | int | Filter by min price, applied when TransactionTypeId = 2
PriceMax | int | Filter by max price, applied when TransactionTypeId = 2
TransactionTypeId | int | 2-For sale &#124; 3-For lease
ZoningTypeGroupId | int | 1-Agricultural &#124; 2-Commercial Mixed &#124; 3-Commercial Office &#124; 4-Commercial Retail &#124; 5-Industrial &#124; 6-Industrial-Heavy &#124; 7-Industrial-Light &#124; 8-Industrial-Medium &#124; 9-Institutional &#124; 10-Other &#124; 11-Recreational &#124; 12-Residential-High Density &#124; 13-Residential-Low Density &#124; 14-Residential - Medium Density
ConstructionStyleId | int | 0-No Preference &#124; 1-Attached &#124; 3-Detached &#124; 5-Semi-detached &#124; 7-Stacked &#124; 9-Link
PropertySearchTypeId | int | 0-No Preference &#124; 1-Residential &#124; 2-Recreational &#124; 3-Condo/Strata &#124; 4-Agriculture &#124; 5-Parking &#124; 6-Vacant Land &#124; 8-Multi Family

## properties/list-residential

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/properties/list-residential?CultureId=1&LatitudeMax=43.8554579&LongitudeMax=-79.1168971&LatitudeMin=43.5810245&LongitudeMin=-79.639219&TransactionTypeId=2&PriceMin=0&RentMin=0&BedRange=0-0&BathRange=0-0&OpenHouse=false&NumberOfDays=0&RecordsPerPage=50&CurrentPage=1&SortBy=1&SortOrder=D" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - OK",
        "Status": "Pins-Via-Cache:false;Sidebar-Items-Via-Cache:0;",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17782"
    },
    "Paging": {
        "RecordsPerPage": 50,
        "CurrentPage": 1,
        "TotalRecords": 6038,
        "MaxRecords": 500,
        "TotalPages": 10,
        "RecordsShowing": 500,
        "Pins": 1896
    },
    "Results": [
        {
            "Id": "22114201",
            "MlsNumber": "C4833856",
            "PublicRemarks": "Awe-Inspiring In Scale & Grandeur In Toronto's Elite Bridle Path Community. Breathtaking Foyer With Dramatic Double Staircase & Iconic Handcrafted Detail Welcomes You Into This World-Class Residence. Spectacular Great Room With Soaring Ceilings. Fabulous Master Bedroom Oasis. Gorgeous Rotunda. Brilliant Natural Light. Timeless Craftsmanship And Exquisitely Proportioned Rooms. In-Law Suite With Elevator. Rare Opportunity For Multigenerational Living.**** EXTRAS **** Spk To La For More Info. Gated Entry To 2-Acre Estate With Manicured Gardens, Outdoor Fireplace, Tennis Court & Custom Fountain. Top Rated Private Schools & Easy Access To Walking/Cycling Trails, Luxury Shopping & Convenient Airport Access. (26948057)",
            "Building": {
                "BathroomTotal": "13",
                "Bedrooms": "5 + 4",
                "StoriesTotal": "2",
                "Type": "House"
            },
            "Individual": [
                {
                    "IndividualID": 1411636,
                    "Name": "DEBRA FELDMAN",
                    "Organization": {
                        "OrganizationID": 276796,
                        "Name": "FOREST HILL REAL ESTATE INC.",
                        "Logo": "https://cdn.realtor.ca/organization/en-CA/TS637513416440000000/lowres/276796.jpg",
                        "Address": {
                            "AddressText": "1440 DON MILLS RD STE 108|TORONTO, Ontario M3B3M1",
                            "PermitShowAddress": true,
                            "DisseminationArea": null
                        },
                        "Phones": [
                            {
                                "PhoneType": "Telephone",
                                "PhoneNumber": "929-4343",
                                "AreaCode": "416",
                                "PhoneTypeId": "1"
                            }
                        ],
                        "OrganizationType": "Firm",
                        "Designation": "Brokerage",
                        "PermitFreetextEmail": true,
                        "PermitShowListingLink": true,
                        "RelativeDetailsURL": "/office/firm/276796/forest-hill-real-estate-inc-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                        "PhotoLastupdate": "2021-03-14 6:00:44 PM"
                    },
                    "Phones": [
                        {
                            "PhoneType": "Telephone",
                            "PhoneNumber": "929-4343",
                            "AreaCode": "416",
                            "PhoneTypeId": "1"
                        }
                    ],
                    "Websites": [
                        {
                            "Website": "http://www.feldmanfinehomes.com",
                            "WebsiteTypeId": "1"
                        }
                    ],
                    "Emails": [
                        {
                            "ContactId": "455714084"
                        }
                    ],
                    "Photo": "https://cdn.realtor.ca/individual/TS637163341800000000/lowres/1122608.jpg",
                    "Position": "Salesperson",
                    "PermitFreetextEmail": true,
                    "FirstName": "DEBRA",
                    "LastName": "FELDMAN",
                    "CorporationDisplayTypeId": "0",
                    "PermitShowListingLink": true,
                    "RelativeDetailsURL": "/agent/1411636/debra-feldman-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                    "AgentPhotoLastUpdated": "2020-02-03 13:43:00",
                    "PhotoHighRes": "https://cdn.realtor.ca/individual/TS637163341800000000/highres/1122608.jpg",
                    "RankMyAgentKey": "",
                    "RealSatisfiedKey": ""
                },
                {
                    "IndividualID": 1897006,
                    "Name": "MATHEW ADAM POTTENS",
                    "Organization": {
                        "OrganizationID": 276796,
                        "Name": "FOREST HILL REAL ESTATE INC.",
                        "Logo": "https://cdn.realtor.ca/organization/en-CA/TS637513416440000000/lowres/276796.jpg",
                        "Address": {
                            "AddressText": "1440 DON MILLS RD STE 108|TORONTO, Ontario M3B3M1",
                            "PermitShowAddress": true,
                            "DisseminationArea": null
                        },
                        "Phones": [
                            {
                                "PhoneType": "Telephone",
                                "PhoneNumber": "929-4343",
                                "AreaCode": "416",
                                "PhoneTypeId": "1"
                            }
                        ],
                        "OrganizationType": "Firm",
                        "Designation": "Brokerage",
                        "PermitFreetextEmail": true,
                        "PermitShowListingLink": true,
                        "RelativeDetailsURL": "/office/firm/276796/forest-hill-real-estate-inc-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                        "PhotoLastupdate": "2021-03-14 6:00:44 PM"
                    },
                    "Phones": [
                        {
                            "PhoneType": "Telephone",
                            "PhoneNumber": "929-4343",
                            "AreaCode": "416",
                            "PhoneTypeId": "1"
                        }
                    ],
                    "Emails": [
                        {
                            "ContactId": "462983949"
                        }
                    ],
                    "Photo": "https://cdn.realtor.ca/individual/TS637159194600000000/lowres/1215009.jpg",
                    "Position": "Broker",
                    "PermitFreetextEmail": true,
                    "FirstName": "MATHEW ADAM",
                    "LastName": "POTTENS",
                    "CccMember": true,
                    "CorporationDisplayTypeId": "0",
                    "PermitShowListingLink": true,
                    "RelativeDetailsURL": "/agent/1897006/mathew-adam-pottens-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                    "AgentPhotoLastUpdated": "2020-01-29 18:31:00",
                    "PhotoHighRes": "https://cdn.realtor.ca/individual/TS637159194600000000/highres/1215009.jpg",
                    "RankMyAgentKey": "",
                    "RealSatisfiedKey": ""
                }
            ],
            "Property": {
                "Price": "$29,800,000",
                "Type": "Single Family",
                "Address": {
                    "AddressText": "71 THE BRIDLE PATH|Toronto, Ontario M3B2B2",
                    "Longitude": "-79.3687317",
                    "Latitude": "43.7356304",
                    "PermitShowAddress": true,
                    "DisseminationArea": null
                },
                "Photo": [
                    {
                        "SequenceId": "1",
                        "HighResPath": "https://cdn.realtor.ca/listings/TS637305224686800000/reb82/highres/6/c4833856_1.jpg",
                        "MedResPath": "https://cdn.realtor.ca/listings/TS637305224686800000/reb82/medres/6/c4833856_1.jpg",
                        "LowResPath": "https://cdn.realtor.ca/listings/TS637305224686800000/reb82/lowres/6/c4833856_1.jpg",
                        "LastUpdated": "2020-07-16 6:54:28 PM"
                    }
                ],
                "Parking": [
                    {
                        "Name": "Garage"
                    }
                ],
                "ParkingSpaceTotal": "31",
                "TypeId": "300",
                "OwnershipType": "Freehold",
                "AmmenitiesNearBy": "Hospital, Park, Public Transit",
                "ConvertedPrice": "$29,800,000 ",
                "OwnershipTypeGroupIds": [
                    1
                ],
                "ParkingType": "Garage",
                "PriceUnformattedValue": "29800000"
            },
            "Business": {},
            "Land": {
                "SizeTotal": "246.38 x 353.63 FT ; Irregular"
            },
            "PostalCode": "M3B2B2",
            "RelativeDetailsURL": "/real-estate/22114201/71-the-bridle-path-toronto-bridle-path-sunnybrook-york-mills",
            "StatusId": "1",
            "PriceChangeDateUTC": "2021-02-19 7:15:27 PM",
            "PhotoChangeDateUTC": "2020-07-16 10:54:29 PM",
            "Distance": "",
            "RelativeURLEn": "/real-estate/22114201/71-the-bridle-path-toronto-bridle-path-sunnybrook-york-mills",
            "RelativeURLFr": "/immobilier/22114201/71-the-bridle-path-toronto"
        },
        ...
    ],
    "Pins": [
        {
            "key": "L9|43.595|-79.5",
            "propertyId": "",
            "count": 1,
            "longitude": "-79.5",
            "latitude": "43.595"
        },
        ...
    ],
    "GroupingLevel": "9"
}
```

This endpoint is used to list residential properties both for rent and for sale

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/properties/list-residential`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
LongitudeMin | double (required) | South West longitude
LatitudeMin | double (required) | South West latitude
LongitudeMax | double (required) | North East longitude
LatitudeMax | double (required) | North East latitude
CurrentPage | int | The current page on which items are displayed 
RecordsPerPage | int | Number items returned per request, max 50
BuildingSizeRange | string | 0-5000:0-5,000 sqft &#124; 5001-10000:5,001-10,000 sqft &#124; 10001-15000:10,001-15,000 sqft &#124; 250001-0:Over 250,000 sqft
BedRange | string | 0-0:Any &#124; 1-1:1 &#124; 1-0:1+ &#124; 2-2:2 &#124; 2-0:2+ &#124; 3-3:3 &#124; 3-0:3+ &#124; 4-4:4 &#124; 4-0:4+ &#124; 5-5:5 &#124; 5-0:5+
BathRange | string | 0-0:Any &#124; 1-1:1 &#124; 1-0:1+ &#124; 2-2:2 &#124; 2-0:2+ &#124; 3-3:3 &#124; 3-0:3+ &#124; 4-4:4 &#124; 4-0:4+ &#124; 5-5:5 &#124; 5-0:5+
UnitRange | string | 0-0:Any &#124; 1-1:1 &#124; 1-0:1+ &#124; 2-2:2 &#124; 2-0:2+ &#124; 3-3:3 &#124; 3-0:3+ &#124; 4-4:4 &#124; 4-0:4+ &#124; 5-5:5 &#124; 5-0:5+ &#124; .... &#124; 9-0:9+
LandSizeRange | string | 0-0:Any &#124; 1-0:1+ acres &#124; 2-0:2+ acres &#124; 5-0:5+ acres &#124; 10-0:10+ acres &#124; 50-0:50+ acres &#124; 100-0:100+ acres &#124; 200-0:200+ acres &#124; 300-0:300+ acres &#124; 400-0:400+ acres &#124; 500-0:500+ acres &#124; 1000-0:1000+ acres
ZoningTypeGroupId | int | 1-Agricultural &#124; 2-Commercial Mixed &#124; 3-Commercial Office &#124; 4-Commercial Retail &#124; 5-Industrial &#124; 6-Industrial-Heavy &#124; 7-Industrial-Light &#124; 8-Industrial-Medium &#124; 9-Institutional &#124; 10-Other &#124; 11-Recreational &#124; 12-Residential-High Density &#124; 13-Residential-Low Density &#124; 14-Residential - Medium Density
ParkingTypeId | int | 1-Attached garage &#124; 2-Integrated garage &#124; 3-Detached garage &#124; 4-Garage &#124; 5-Carport &#124; 6-Underground &#124; 7-Indoor &#124; 8-Open &#124; 9-Covered &#124; 10-Parking pad &#124; 11-Paved Yard &#124; 35-Boat House &#124; 36-Concrete &#124; 37-Heated Garage
RentMin | int | Filter by min price, applied when TransactionTypeId = 3
RentMax | int | Filter by max price, applied when TransactionTypeId = 3
PriceMin | int | Filter by min price, applied when TransactionTypeId = 2
PriceMax | int | Filter by min price, applied when TransactionTypeId = 2
TransactionTypeId | int | 2-For sale &#124; 3-For rent
NumberOfDays | int | Listed since
OpenHouseStartDate | string | Format date as MM/dd/yyyy, ex : 03/20/2020
OpenHouseEndDate | string | Format date as MM/dd/yyyy, ex : 03/31/2020
OpenHouse | boolean | false/true - Need to use together with OpenHouseStartDate and OpenHouseEndDate parameters
CultureId | int | 1 - English &#124; 2 - French
SortOrder | string | A - ascending &#124; D - descending
SortBy | int | 1-Price($) &#124; 6-Date &#124; 11-Virtual Tour &#124; 12-Open Houses &#124; 13-More Photos
BuildingTypeId | int | 0-No Preference &#124; 1-House &#124; 2-Duplex &#124; 3-Triplex &#124; 5-Residential Commercial Mix &#124; 6-Mobile Home &#124; 12-Special Purpose &#124; 14-Other &#124; 16-Row / Townhouse &#124; 17-Apartment &#124; 19-Fourplex &#124; 20-Garden Home &#124; 26-Modular &#124; 27-Manufactured Home/Mobile &#124; 28-Commercial Apartment &#124; 29-Manufactured Home
Keywords | string | Get suitable values from .../keywords/list endpoint, separated by comma for multiple keywords, Ex : Inlaw suite,Income suite
FarmTypeId | int | 0-No Preference &#124; 1-Animal &#124; 2-Boarding &#124; 3-Cash Crop &#124; 4-Feed Lot &#124; 5-Nursery &#124; 6-Market Gardening &#124; 7-Hobby Farm &#124; 8-Vineyard &#124; 9-Orchard &#124; 10-Greenhouse &#124; 12-Mixed
PropertySearchTypeId | int | 0-No Preference &#124; 1-Residential &#124; 2-Recreational &#124; 3-Condo/Strata &#124; 4-Agriculture &#124; 5-Parking &#124; 6-Vacant Land &#124; 8-Multi Family
ConstructionStyleId | int | 0-No Preference &#124; 1-Attached &#124; 3-Detached &#124; 5-Semi-detached &#124; 7-Stacked &#124; 9-Link

## properties/list-by-mls

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/properties/list-by-mls?CultureId=1&ReferenceNumber=C4833856" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - OK",
        "Status": "Pins-Via-Cache:false;Sidebar-Items-Via-Cache:0;",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17831"
    },
    "Paging": {
        "RecordsPerPage": 9,
        "CurrentPage": 1,
        "TotalRecords": 1,
        "MaxRecords": 500,
        "TotalPages": 1,
        "RecordsShowing": 1,
        "Pins": 0
    },
    "Results": [
        {
            "Id": "22114201",
            "MlsNumber": "C4833856",
            "PublicRemarks": "Awe-Inspiring In Scale & Grandeur In Toronto's Elite Bridle Path Community. Breathtaking Foyer With Dramatic Double Staircase & Iconic Handcrafted Detail Welcomes You Into This World-Class Residence. Spectacular Great Room With Soaring Ceilings. Fabulous Master Bedroom Oasis. Gorgeous Rotunda. Brilliant Natural Light. Timeless Craftsmanship And Exquisitely Proportioned Rooms. In-Law Suite With Elevator. Rare Opportunity For Multigenerational Living.**** EXTRAS **** Spk To La For More Info. Gated Entry To 2-Acre Estate With Manicured Gardens, Outdoor Fireplace, Tennis Court & Custom Fountain. Top Rated Private Schools & Easy Access To Walking/Cycling Trails, Luxury Shopping & Convenient Airport Access. (26948057)",
            "Building": {
                "BathroomTotal": "13",
                "Bedrooms": "5 + 4",
                "StoriesTotal": "2",
                "Type": "House"
            },
            "Individual": [
                {
                    "IndividualID": 1411636,
                    "Name": "DEBRA FELDMAN",
                    "Organization": {
                        "OrganizationID": 276796,
                        "Name": "FOREST HILL REAL ESTATE INC.",
                        "Logo": "https://cdn.realtor.ca/organization/en-CA/TS637513416440000000/lowres/276796.jpg",
                        "Address": {
                            "AddressText": "1440 DON MILLS RD STE 108|TORONTO, Ontario M3B3M1",
                            "PermitShowAddress": true,
                            "DisseminationArea": null
                        },
                        "Phones": [
                            {
                                "PhoneType": "Telephone",
                                "PhoneNumber": "929-4343",
                                "AreaCode": "416",
                                "PhoneTypeId": "1"
                            }
                        ],
                        "OrganizationType": "Firm",
                        "Designation": "Brokerage",
                        "PermitFreetextEmail": true,
                        "PermitShowListingLink": true,
                        "RelativeDetailsURL": "/office/firm/276796/forest-hill-real-estate-inc-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                        "PhotoLastupdate": "2021-03-14 6:00:44 PM"
                    },
                    "Phones": [
                        {
                            "PhoneType": "Telephone",
                            "PhoneNumber": "929-4343",
                            "AreaCode": "416",
                            "PhoneTypeId": "1"
                        }
                    ],
                    "Websites": [
                        {
                            "Website": "http://www.feldmanfinehomes.com",
                            "WebsiteTypeId": "1"
                        }
                    ],
                    "Emails": [
                        {
                            "ContactId": "455714084"
                        }
                    ],
                    "Photo": "https://cdn.realtor.ca/individual/TS637163341800000000/lowres/1122608.jpg",
                    "Position": "Salesperson",
                    "PermitFreetextEmail": true,
                    "FirstName": "DEBRA",
                    "LastName": "FELDMAN",
                    "CorporationDisplayTypeId": "0",
                    "PermitShowListingLink": true,
                    "RelativeDetailsURL": "/agent/1411636/debra-feldman-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                    "AgentPhotoLastUpdated": "2020-02-03 13:43:00",
                    "PhotoHighRes": "https://cdn.realtor.ca/individual/TS637163341800000000/highres/1122608.jpg",
                    "RankMyAgentKey": "",
                    "RealSatisfiedKey": ""
                },
                ...
            ],
            "Property": {
                "Price": "$29,800,000",
                "Type": "Single Family",
                "Address": {
                    "AddressText": "71 THE BRIDLE PATH|Toronto, Ontario M3B2B2",
                    "Longitude": "-79.3687317",
                    "Latitude": "43.7356304",
                    "PermitShowAddress": true,
                    "DisseminationArea": null
                },
                "Photo": [
                    {
                        "SequenceId": "1",
                        "HighResPath": "https://cdn.realtor.ca/listings/TS637305224686800000/reb82/highres/6/c4833856_1.jpg",
                        "MedResPath": "https://cdn.realtor.ca/listings/TS637305224686800000/reb82/medres/6/c4833856_1.jpg",
                        "LowResPath": "https://cdn.realtor.ca/listings/TS637305224686800000/reb82/lowres/6/c4833856_1.jpg",
                        "LastUpdated": "2020-07-16 6:54:28 PM"
                    }
                ],
                "Parking": [
                    {
                        "Name": "Garage"
                    }
                ],
                "ParkingSpaceTotal": "31",
                "TypeId": "300",
                "OwnershipType": "Freehold",
                "AmmenitiesNearBy": "Hospital, Park, Public Transit",
                "ConvertedPrice": "$29,800,000 ",
                "OwnershipTypeGroupIds": [
                    1
                ],
                "ParkingType": "Garage",
                "PriceUnformattedValue": "29800000"
            },
            "Business": {},
            "Land": {
                "SizeTotal": "246.38 x 353.63 FT ; Irregular"
            },
            "PostalCode": "M3B2B2",
            "RelativeDetailsURL": "/real-estate/22114201/71-the-bridle-path-toronto-bridle-path-sunnybrook-york-mills",
            "StatusId": "1",
            "PriceChangeDateUTC": "2021-02-19 7:15:27 PM",
            "PhotoChangeDateUTC": "2020-07-16 10:54:29 PM",
            "Distance": "",
            "RelativeURLEn": "/real-estate/22114201/71-the-bridle-path-toronto-bridle-path-sunnybrook-york-mills",
            "RelativeURLFr": "/immobilier/22114201/71-the-bridle-path-toronto"
        }
    ],
    "Pins": [],
    "GroupingLevel": ""
}
```

This endpoint is used to list properties by listing ID or MLS number

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/properties/list-by-mls`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
ReferenceNumber | string (required) | List ID or MLS number
CultureId | int | 1 - English &#124; 2 - French

## properties/detail

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/properties/detail?CultureId=1&ReferenceNumber=C4833856&PropertyID=22114201&PreferedMeasurementUnit=1" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - OK",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17782"
    },
    "HashCode": "880180196",
    "Id": "22114201",
    "MlsNumber": "C4833856",
    "PublicRemarks": "Awe-Inspiring In Scale & Grandeur In Toronto's Elite Bridle Path Community. Breathtaking Foyer With Dramatic Double Staircase & Iconic Handcrafted Detail Welcomes You Into This World-Class Residence. Spectacular Great Room With Soaring Ceilings. Fabulous Master Bedroom Oasis. Gorgeous Rotunda. Brilliant Natural Light. Timeless Craftsmanship And Exquisitely Proportioned Rooms. In-Law Suite With Elevator. Rare Opportunity For Multigenerational Living.**** EXTRAS **** Spk To La For More Info. Gated Entry To 2-Acre Estate With Manicured Gardens, Outdoor Fireplace, Tennis Court & Custom Fountain. Top Rated Private Schools & Easy Access To Walking/Cycling Trails, Luxury Shopping & Convenient Airport Access. (26948057)",
    "LastUpdated": "2021-03-14 6:00:44 PM",
    "Building": {
        "BathroomTotal": "13",
        "Bedrooms": "5 + 4",
        "StoriesTotal": "2",
        "Type": "House",
        "Age": "",
        "BasementDevelopment": "Finished",
        "BasementFeatures": "Separate entrance",
        "BasementType": "N/A (Finished)",
        "ConstructionStyleAttachment": "Detached",
        "CoolingType": "Central air conditioning",
        "ExteriorFinish": "Stone",
        "HeatingFuel": "Natural gas",
        "HeatingType": "Forced air (Natural gas)",
        "Room": [
            {
                "Type": "Living room",
                "Width": "6.17 m",
                "Length": "8.56 m",
                "Level": "Main level",
                "Dimension": "8.56 m x 6.17 m"
            },
            ...
        ],
        "DisplayAsYears": "2",
        "FireplacePresent": "Yes"
    },
    "Land": {
        "SizeTotal": "246.38 x 353.63 FT ; Irregular"
    },
    "Individual": [
        {
            "IndividualID": 1411636,
            "Name": "DEBRA FELDMAN",
            "Organization": {
                "OrganizationID": 276796,
                "Name": "FOREST HILL REAL ESTATE INC.",
                "Logo": "https://cdn.realtor.ca/organization/en-CA/TS637513416440000000/lowres/276796.jpg",
                "Address": {
                    "AddressText": "1440 DON MILLS RD STE 108|TORONTO, Ontario M3B3M1",
                    "PermitShowAddress": true,
                    "DisseminationArea": null
                },
                "Phones": [
                    {
                        "PhoneType": "Telephone",
                        "PhoneNumber": "929-4343",
                        "AreaCode": "416",
                        "PhoneTypeId": "1"
                    }
                ],
                "OrganizationType": "Firm",
                "Designation": "Brokerage",
                "PermitFreetextEmail": true,
                "PermitShowListingLink": true,
                "RelativeDetailsURL": "/office/firm/276796/forest-hill-real-estate-inc-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
                "PhotoLastupdate": "2021-03-14 6:00:44 PM"
            },
            "Phones": [
                {
                    "PhoneType": "Telephone",
                    "PhoneNumber": "929-4343",
                    "AreaCode": "416",
                    "PhoneTypeId": "1"
                }
            ],
            "Websites": [
                {
                    "Website": "http://www.feldmanfinehomes.com",
                    "WebsiteTypeId": "1"
                }
            ],
            "Emails": [
                {
                    "ContactId": "455714084"
                }
            ],
            "Photo": "https://cdn.realtor.ca/individual/TS637163341800000000/lowres/1122608.jpg",
            "Position": "Salesperson",
            "PermitFreetextEmail": true,
            "FirstName": "DEBRA",
            "LastName": "FELDMAN",
            "CorporationDisplayTypeId": "0",
            "PermitShowListingLink": true,
            "RelativeDetailsURL": "/agent/1411636/debra-feldman-1440-don-mills-rd-ste-108-toronto-ontario-m3b3m1",
            "AgentPhotoLastUpdated": "2020-02-03 13:43:00",
            "PhotoHighRes": "https://cdn.realtor.ca/individual/TS637163341800000000/highres/1122608.jpg",
            "RankMyAgentKey": "",
            "RealSatisfiedKey": ""
        },
        ...
    ],
    "Property": {
        "Price": "$29,800,000",
        "Type": "Single Family",
        "Address": {
            "AddressText": "71 THE BRIDLE PATH|Toronto, Ontario M3B2B2",
            "Longitude": "-79.3687317",
            "Latitude": "43.7356304",
            "CommunityName": "Bridle Path-Sunnybrook-York Mills",
            "PermitShowAddress": true,
            "DisseminationArea": "35202630"
        },
        "Photo": [
            {
                "SequenceId": "1",
                "HighResPath": "https://cdn.realtor.ca/listing/TS637305224686800000/reb82/highres/6/c4833856_1.jpg",
                "MedResPath": "https://cdn.realtor.ca/listing/TS637305224686800000/reb82/medres/6/c4833856_1.jpg",
                "LowResPath": "https://cdn.realtor.ca/listing/TS637305224686800000/reb82/lowres/6/c4833856_1.jpg",
                "LastUpdated": "2020-07-16 6:54:28 PM"
            },
            ...
        ],
        "Parking": [
            {
                "Name": "Garage"
            }
        ],
        "ParkingSpaceTotal": "31",
        "TypeId": "300",
        "OwnershipType": "Freehold",
        "AmmenitiesNearBy": "Hospital, Park, Public Transit",
        "OwnershipTypeGroupIds": [
            1
        ],
        "ParkingType": "Garage",
        "PriceUnformattedValue": "29800000",
        "PoolType": "Indoor pool",
        "TransactionType": "For sale",
        "TaxAmount": "$128,774.44"
    },
    "UploadedBy": "Toronto Regional Real Estate Board",
    "Business": {},
    "RelativeURLEn": "/real-estate/22114201/71-the-bridle-path-toronto-bridle-path-sunnybrook-york-mills",
    "RelativeURLFr": "/immobilier/22114201/71-the-bridle-path-toronto",
    "History": [],
    "UploadedByWebsite": "http://www.trebhome.com/",
    "UploadedByAddress": {
        "AddressText": "1400 Don Mills Road, Toronto, Ontario M3B 3N1",
        "PermitShowAddress": true,
        "DisseminationArea": null
    }
}
```

This endpoint is used to get details information of specific property

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/properties/detail`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
ReferenceNumber | string (required) | The value of MlsNumber field from list-commercial or list-residential endpoints
PropertyID | int (required) | The value of Id field from list-commercial or list-residential endpoints
PreferedMeasurementUnit | int | 1-Metric &#124; 2-Imperial
CultureId | int | 1 - English &#124; 2 - French

## properties/get-statistics

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/properties/get-statistics?CultureId=1&Longitude=-85.8230136&Latitude=49.1241922" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - OK",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17831"
    },
    "Data": [
        {
            "key": "",
            "value": [
                {
                    "key": "Daytime Population",
                    "value": "204"
                },
                ...
            ]
        },
        ...
    ]
}
```

This endpoint is used to get statistic information of surround area by GEO location

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/properties/get-statistics`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
Latitude | double (required) | Latitude of specific location
Longitude | double (required) | Longitude of specific location
CultureId | int | 1 - English &#124; 2 - French

## keywords/list

```shell
curl "https://realtor-canadian-real-estate.p.rapidapi.com/keywords/list" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: realtor-canadian-real-estate.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ErrorCode": {
        "Id": 200,
        "Description": "Success - OK",
        "ProductName": "! Push to PR-Stage - Realtor API (Maintenance)^30626 [Friday, March 26, 2021 9:52:23 AM]",
        "Version": "1.0.7755.17831"
    },
    "Words": [
        {
            "Id": "1",
            "Value": "Hot tub",
            "CultureId": "1"
        },
        ...
    ]
}
```

This endpoint is used to list all supported tags/keywords for filtering

### HTTP Request

`GET https://realtor-canadian-real-estate.p.rapidapi.com/keywords/list`

# Trip Advisor API
 
## airports/search

```shell
curl "https://tripadvisor1.p.rapidapi.com/airports/search?query=Chiangmai&locale=en_US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "code": "CNX",
        "country_code": "TH",
        "name": "Chiang Mai Intl Airport",
        "city_name": "Chiang Mai",
        "display_name": "Chiang Mai, Thailand - Chiang Mai Intl (CNX)",
        "display_title": "Chiang Mai, Thailand",
        "display_sub_title": "Chiang Mai Intl (CNX)",
        "location_id": 293917,
        "time_zone_name": "Asia/Bangkok",
        "latitude": 18.771944,
        "longitude": 98.96833
    }
]
```

This endpoint is used to search for airport code by countries', cities', etc... name

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/airports/search`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
query | string (required) | Name of cities, districts, places, etc...
locale | string | The language code

## flights/create-session

```shell
curl "https://tripadvisor1.p.rapidapi.com/flights/create-session?o1=CNX&d1=DMK&dd1=2021-04-02&currency=USD&c=0&ta=1" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to create new session for searching flights tickets of all airlines around the world. The flight APIs need to use as following : 
Firstly, you init a search session by using the create-session endpoint and get sid value.
Secondly, you repeatedly call poll endpoint until the summary/c field is true to get final total flight by summary/nr value. o parameter must be 0 otherwise the summary field is not returned. 
Thirdly, you repeatedly call poll endpoint with o increasing by n value step by step until you reach total flight.

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/flights/create-session`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
o1 | string (required) | Airport code of first origin
d1 | string (required) | The airport code of first destination location
dd1 | string (required) | The date of departure from first origin, the format is yyyy-MM-dd. Ex : 2020-05-15
currency | string | The currency code. Ex : USD
o2 | string | The airport code of second origin location
d2 | string | The airport code of second destination location
dd2 | string | The departure date of second origin, the format is yyyy-MM-dd. Ex : 2020-05-15
ta | NUMBER | The number of adults
ts | NUMBER | The number of seniors
tc | string | The age of every children separated by comma. Ex : 11,5
c | int | Cabin code, such as 0 - Economy | 1- Business Class | 2 - First Class | 3 - Premium Economy 

## flights/poll

```shell
curl "https://tripadvisor1.p.rapidapi.com/flights/poll?currency=USD&sid=3180233b-7155-4c56-84d4-646f5c7dd628.710&so=PRICE&am=&ca&mc=&ns=&n=15&o=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to Poll for more available flight data until the value of "summary/c" field returned right in this endpoint is true. The flight APIs need to use as following : Firstly, you init a search session by using the create-session endpoint and get sid value Secondly, you repeatedly call poll endpoint until the summary/c field is true to get final total flight by summary/nr value. o parameter must be 0 otherwise the summary field is not returned. Thirdly, you repeatedly call poll endpoint with o increasing by n value step by step until you reach total flight.

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/flights/poll`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
sid | string (required) | The value of sid returned in flights/create-session endpoint
currency | string | The currency code
n | int | The number of items per response (max 15)
o | int | The offset of items to be ignored in response for paging. Use summary/nr field returned in response to get total flights
mc | string | Check for suitable value of "summary/cp" or "summary/ocp" field (separated by comma to specify multiple values) returned in flights/create-session or right in this endpoint
ca | string | Check for suitable value of "summary/ap" field (separated by comma to specify multiple values) returned in flights/create-session or right in this endpoint
ns | string | One of following NON_STOP | ONE_STOP | TWO_PLUS or separated by comma to specify multiple values
so | string | Check for suitable value of "so" field returned in flights/create-session or right in this endpoint
am | string | Check for suitable value of "itineraries/ac" field (separated by comma to specify multiple values) returned in flights/create-session or right in this endpoint

## flights/get-booking-url

```shell
curl "https://tripadvisor1.p.rapidapi.com/flights/get-booking-url?searchId=5aaa20e5-d5c8-4cdd-a657-b6453bb80756.1483&searchHash=2188ff0ed4e8e4ee7a50dc32b229e11d&id=AgodaFlights|1|68&impressionId=372e5654-b873-4c26-859b-633c29f7ad84.93175&Orig=NYC&Dest=HAN" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to generate booking url relating to a specific flight

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/flights/get-booking-url`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
searchHash | string (required) | The value of summary/sh field returned in response of .../flights/create-session endpoint. For example : 2188ff0ed4e8e4ee7a50dc32b229e11d
Dest | string (required) | Airport code of destination. For example : NYC
id | string (required) | The value of itineraries/l/id field returned in response of .../flights/poll endpoint. For example : AgodaFlights|1|68
Orig | string (required) | Airport code of origin. For example : DMK
searchId | string (required) | The value of search_params/sid field returned in response of .../flights/create-session endpoint. For example : 5aaa20e5-d5c8-4cdd-a657-b6453bb80756.1483
impressionId | string | The value of itineraries/l/impressionId field returned in response of .../flights/poll endpoint. For example : 372e5654-b873-4c26-859b-633c29f7ad84.93175

## locations/auto-complete

```shell
curl "https://tripadvisor1.p.rapidapi.com/locations/auto-complete?query=chiang mai&lang=en_US&units=km" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list suggested locations by term or phrase

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/locations/auto-complete`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
query | string (required) | Name of cities, districts, places, etc...
lang | string | The language code
units | string | One of the followings : km|mi

## locations/search

```shell
curl "https://tripadvisor1.p.rapidapi.com/locations/search?query=eiffel tower&lang=en_US&units=km&location_id=1&currency=USD&limit=30&offset=0&sort=relevance" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to search for related cities, countries, and suggestions

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/locations/search`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | string (required) | The value of location_id field returned right in this endpoint or .../locations/auto-complete endpoint
limit | int | The number of items per response (max 30)
sort | string | One of the followings : relevance|distance
offset | int | The number of items to ignore for paging purpose
lang | string | The language code
currency | string | The currency code
units | string | One of the followings : km|mi
query | string | Name of cities, districts, places, etc... 

## hotels/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/hotels/list?location_id=12397144&rooms=1&adults=1&checkin=2020-10-13&nights=1&limit=30&offset=0&currency=USD&lang=en_US&sort=recommended" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list all hotels around the world with options and filters

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/hotels/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in locations/search endpoint
adults | int (required) | The number of adults in all rooms
checkin | string (required) | The check-in date at hotel, the format is yyyy-MM-dd. Ex : 2020-05-15
rooms | int (required) | The number of rooms
nights | int (required) | The number of nights to live
limit | int | The number of items per response (max 30)
offset | int | The number of items to ignore for paging purpose
sort | string | One of the followings : recommended|popularity|price
order | string | One of the followings : asc|desc, this param is used with sort by price
currency | string | The currency code
child_rm_ages | string | The age of every children separated by comma in all rooms. Ex : 7,10
lang | string | The language code
zff | string | Hotel Style - Check for suitable value of filters/zff field (separated by comma to filter by multiple values. Ex : 4,6) returned in hotel-filters/list endpoint
pricesmin | int | Check for suitable price range in filters/prices_slider field returned in hotel-filters/list endpoint. For exmaple : $10 -> 10
pricesmax | int | Check for suitable price range in filters/prices_slider field returned in hotel-filters/list endpoint. For exmaple : $120 -> 120
subcategory | string | Check for suitable value of filters/subcategory field (separated by comma to filter by multiple values. Ex : hotel,bb,specialty) returned in hotel-filters/list endpoint
hotel_class | string | Check for suitable value of filters/hotel_class field (separated by comma to filter by multiple values. Ex : 1,2,3) returned in hotel-filters/list endpoint
amenities | string | Check for suitable value of filters/amenities field (separated by comma to filter by multiple values. Ex : beach,bar_lounge,airport_transportation) returned in hotel-filters/list endpoint

## hotel-filters/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/hotel-filters/list?location_id=297684&rooms=1&adults=1&checkin=2020-09-29&nights=1&limit=10&offset=0&currency=USD&lang=en_US&sort=recommended" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list all available options and filters

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/hotel-filters/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in locations/search endpoint
checkin | string (required) | The check-in date at hotel
adults | int (required) | The number of adults in all rooms
rooms | int (required) | The number of rooms
nights | int (required) | The number of nights to live
order | string | One of the followings asc|desc, this param is used with sort by price
sort | string | One of the followings recommended|popularity|price
lang | string | The language code
currency | string | The currency code
child_rm_ages | string | The age of every children separated by comma in all rooms
subcategory | string | Check for suitable value of "filters/subcategory" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
pricesmin | int | Check for suitable price range in "filters/prices_slider" field returned in hotel-filters/list endpoint. For exmaple : $10 -> 10
pricesmax | int | Check for suitable price range in "filters/prices_slider" field returned in hotel-filters/list endpoint. For exmaple : $120 -> 120
zff | string | Hotel Style - Check for suitable value of "filters/zff" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
hotel_class | string | Check for suitable value of "filters/hotel_class" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
amenities | string | Check for suitable value of "filters/amenities" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint

## hotels/list-in-boundary

```shell
curl "https://tripadvisor1.p.rapidapi.com/hotels/list-in-boundary?bl_latitude=11.847676067496902&bl_longitude=108.4732099995017&tr_latitude=12.838442658260522&tr_longitude=109.14935935288666&rooms=1&adults=1&checkin=2020-06-12&nights=1&limit=50&offset=0&currency=USD&lang=en_US&sort=price&order=asc" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list hotels by specifying coordinates of bottom left and top right of boundary

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/hotels/list-in-boundary`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
tr_latitude | double (required) | Latitude of top right coordinate
tr_longitude | double (required) | Longitude of top right coordinate
bl_latitude | double (required) | Latitude of bottom left coordinate
bl_longitude | double (required) | Longitude of bottom left coordinate
adults | int | The number of adults in all rooms
limit | int | The number of items per response (max 30)
offset | int | The number of items to ignore for paging purpose
currency | string | The currency code
pricesmin | int | Check for suitable price range in filters/prices_slider field returned in hotel-filters/list endpoint. For exmaple : $10 -> 10
pricesmax | int | Check for suitable price range in filters/prices_slider field returned in hotel-filters/list endpoint. For exmaple : $120 -> 120
rooms | int | The number of rooms
zff | string | Hotel Style - Check for suitable value of "filters/zff" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
subcategory | string | Check for suitable value of "filters/subcategory" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
hotel_class | string | Check for suitable value of "filters/hotel_class" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
child_rm_ages | string | The age of every children separated by comma in all rooms
amenities | string | Check for suitable value of filters/amenities field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint

## hotels/list-by-latlng

```shell
curl "https://tripadvisor1.p.rapidapi.com/hotels/list-by-latlng?latitude=41.899297&longitude=-87.6256441&rooms=1&adults=1&checkin=2020-06-25&nights=1&limit=50&offset=0&currency=USD&lang=en_US&sort=price&order=asc" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list hotels around a coordinate and radius

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/hotels/list-by-latlng`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
latitude | double (required) | Latitude of coordinate
longitude | double (required) | Longitude of coordinate
nights | string | The number of nights to live
checkin | string  | The check-in date at hotel
adults | int | The number of adults in all rooms
rooms | int | The number of rooms
lang | string | The language code
offset | int | The number of items to ignore for paging purpose
limit | int | The number of items per response (max 30)
distance | int | The radius to look for nearest places
currency | string | The currency code
hotel_class | string | Check for suitable value of filters/hotel_class field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
amenities | string | Check for suitable value of filters/amenities field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
child_rm_ages | string | The age of every children separated by comma in all rooms
pricesmin | int | Check for suitable price range in filters/prices_slider field returned in hotel-filters/list endpoint. For exmaple : $10 -> 10
pricesmax | int | Check for suitable price range in filters/prices_slider field returned in hotel-filters/list endpoint. For exmaple : $120 -> 120
zff | string | Hotel Style - Check for suitable value of "filters/zff" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
subcategory | string | Check for suitable value of filters/subcategory field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint

## hotels/get-details

```shell
curl "https://tripadvisor1.p.rapidapi.com/hotels/get-details?location_id=8014024&rooms=1&adults=2&checkin=2020-06-24&nights=2&currency=USD&lang=en_US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to get all information of hotels

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/hotels/get-details`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in hotels/list endpoint
checkin | string (required) | The check-in date at hotel
adults | int (required) | The number of adults in all rooms
nights | string (required) | The number of nights to live
currency | string | The currency code
rooms | int (required) | The number of rooms
lang | string | The language code
child_rm_ages | string | The age of every children separated by comma in all rooms

## restaurants/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/restaurants/list?location_id=293928&restaurant_mealtype=all&restaurant_tagcategory=10591&restaurant_tagcategory_standalone=10591&combined_food=all&limit=30&offset=30&lunit=km&currency=USD&lang=en_US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list restaurants by location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/restaurants/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in locations/search endpoint
restaurant_tagcategory_standalone | string | Establishment Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
lunit | string | One of the followings km|mi
currency | string | The currency code
offset | int | The number of items to ignore for paging purpose
limit | int | The number of items per response (max 30)
lang | string | The language code
restaurant_tagcategory | string | Establishment Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
dietary_restrictions | string | Dietary Restrictions - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
prices_restaurants | string | Prices - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to filter by multiple values. Ex : 10953,10955) returned right in this endpoint
restaurant_mealtype | string | Meals - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to filter by multiple values. Ex : 10598,10599) returned right in this endpoint
min_rating | int | Min 3 - Max 5
combined_food | string | Cuisine Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
open_now | boolean | Only returns restaurants which are opening now
restaurant_dining_options | string | Restaurant Features - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
restaurant_styles | string | Restaurant Features - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint

## restaurants/list-in-boundary

```shell
curl "https://tripadvisor1.p.rapidapi.com/restaurants/list-in-boundary?bl_latitude=12.113245&bl_longitude=109.095887&tr_latitude=12.346705&tr_longitude=109.262909&restaurant_mealtype=all&restaurant_tagcategory=10591&restaurant_tagcategory_standalone=10591&dietary_restrictions=all&limit=30&offset=0&lunit=km&currency=USD&lang=en_US&combined_food=all" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list restaurants by specifying coordinates of bottom left and top right of a boundary

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/restaurants/list-in-boundary`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
bl_latitude | double (required) | Latitude of bottom left coordinate
bl_longitude | double (required) | Longitude of bottom left coordinate
tr_latitude | double (required) | Latitude of top right coordinate
tr_longitude | double (required) | Longitude of top right coordinate
dietary_restrictions | string | Dietary Restrictions - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
min_rating | int | Rating - Min 3, max 5
lunit | string | One of the followings km|mi
combined_food | string | Cuisine Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
restaurant_tagcategory | string | Establishment Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
limit | int | The number of items per response (max 30)
currency | string | The currency code
offset | int | The number of items to ignore for paging purpose
prices_restaurants | string | Prices - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to filter by multiple values. Ex : 10953,10955) returned right in this endpoint
restaurant_tagcategory_standalone | string | Establishment Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
restaurant_mealtype | string | Meals - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to filter by multiple values. Ex : 10598,10599) returned right in this endpoint
lang | string | The language code
restaurant_dining_options | string | Restaurant Features - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
restaurant_styles | string | Restaurant Features - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
open_now | boolean | Only returns restaurants which are opening now

## restaurants/list-by-latlng

```shell
curl "https://tripadvisor1.p.rapidapi.com/restaurants/list-by-latlng?latitude=12.235588&longitude=109.19553&distance=2&restaurant_mealtype=all&restaurant_tagcategory=10591&restaurant_tagcategory_standalone=10591&dietary_restrictions=all&combined_food=all&lunit=km&currency=USD&lang=en_US&limit=30&offset=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list restaurants by specifying an coordinate and radius

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/restaurants/list-by-latlng`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
latitude | double (required) | Latitude of coordinate
longitude | double (required) | Longitude of coordinate
limit | int | The number of items per response (max 30)
currency | string | The currency code
restaurant_dining_options | string | Restaurant Features - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
prices_restaurants | string | Prices - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
restaurant_styles | string | Restaurant Features - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
combined_food | string | Cuisine Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
distance | int | The radius around specified coordinate (max 10)
restaurant_tagcategory | string | Establishment Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
restaurant_mealtype | string | Meals - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
open_now | BOOLEAN | Only returns restaurants which are opening now
offset | int | The number of items to ignore for paging purpose
dietary_restrictions | string | Dietary Restrictions - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
lunit | string | One of the followings km|mi
lang | string | The language code
restaurant_tagcategory_standalone | string | Establishment Type - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (separated by comma to specify multiple values) returned right in this endpoint
min_rating | int | Min 3 - Max 5

## restaurants/get-details

```shell
curl "https://tripadvisor1.p.rapidapi.com/restaurants/get-details?location_id=9782025&currency=USD&lang=en_US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to get all information of a specific restaurant by its location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/restaurants/get-details`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in restaurants/list endpoint
lang | string | The language code
currency | string | The currency code

## attractions/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/attractions/list?location_id=298571&subcategory=0&sort=ranking&lunit=km&currency=USD&lang=en_US&limit=30&offset=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list attractions by location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/attractions/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in locations/search endpoint
lang | string | The language code
currency | string | The currency code
sort | string | One of following recommended|ranking
lunit | string | One of the followings km|mi
offset | int | The number of items to ignore for paging purpose
min_rating | int | Rating - Min 3 max 5
limit | int | The number of items per response (max 30)
bookable_first | BOOLEAN | Book online first
subcategory | int | Attraction category - Check for suitable values of filters_v2/filter_sections/filter_groups/options/value field (only one value is allowed at a time) returned right in this endpoint

## attractions/list-by-latlng

```shell
curl "https://tripadvisor1.p.rapidapi.com/attractions/list-by-latlng?latitude=12.235588&longitude=109.19553&lunit=km&currency=USD&lang=en_US&limit=30&offset=60&distance=25" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list attractions by specifying an coordinate and radius

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/attractions/list-by-latlng`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
longitude | double (required) | Longitude of coordinate
latitude | double (required) | Latitude of coordinate
lunit | string | One of the followings km|mi
currency | string | The currency code
offset | int | The number of items to ignore for paging purpose lunit
limit | int | The number of items per response (max 30)
distance | int | The radius around specified coordinate (max 25)
lang | string | The language code

## attractions/list-in-boundary

```shell
curl "https://tripadvisor1.p.rapidapi.com/attractions/list-in-boundary" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list attractions by specifying coordinates of bottom left and top right of a boundary

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/attractions/list-in-boundary`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
tr_longitude | double (required) | Longitude of top right coordinate
tr_latitude | double (required) | Latitude of top right coordinate
bl_longitude | double (required) | Longitude of bottom left coordinate
bl_latitude | double (required) | Latitude of bottom left coordinate
offset | int | The number of items to ignore for paging purpose
min_rating | int | Rating - Min 3 max 5
currency | string | The currency code
bookable_first | boolean | Book online first
limit | int | The number of items per response (max 30)
lunit | string | One of the followings km|mi
lang | string | The language code
subcategory | int | Attraction category - Check for suitable values of filters&#95;v2/filter&#95;sections/filter&#95;groups/options/value field (only one value is allowed at a time) returned right in this endpoint

## attractions/get-details

```shell
curl "https://tripadvisor1.p.rapidapi.com/attractions/get-details?location_id=1451754&currency=USD&lang=en_US" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to get all information of specific attracting location by its location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/attractions/get-details`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in attractions/list endpoint
currency | string | The currency code
lang | string | The language code

## questions/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/questions/list?location_id=8014024&limit=10&offset=10" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list questions related to a location by its id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/questions/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in hotels/list, restaurants/list, or attractions/list endpoints
offset | int | The number of items to ignore for paging purpose
limit | int | The number of items per response (max 10)

## answers/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/answers/list?question_id=5283833&limit=10&offset=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list answers related to a questions by its id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/answers/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
question_id | int (required) | The value of id field that returned in questions/list endpoint 
offset | int | The number of items to ignore for paging purpose
limit | int | The number of items per response (max 10)

## photos/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/photos/list?location_id=2233968&currency=USD&lang=en_US&limit=50&offset=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list photos related to a location by its id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/photos/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in hotels/list, restaurants/list, or attractions/list endpoints
offset | int | The number of items to ignore for paging purpose
lang | string | The language code
currency | string | The currency code
limit | int | The number of items per response (max 50)

## tips/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/tips/list?location_id=8014024&currency=USD&lang=en_US&limit=20&offset=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list tips of specific hotel by its location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/tips/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in hotels/list endpoint
lang | string | The language code
currency | string | The currency code
offset | int | The number of items to ignore for paging purpose
limit | int | The number of items per response (max 20)

## reviews/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/reviews/list?location_id=8014024&currency=USD&lang=en_US&limit=20&offset=0&keyword" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list reviews related to a location by its location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/reviews/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in hotels/list, restaurants/list, or attractions/list endpoints
limit | int | The number of items per response (max 20)
currency | string | The currency code
offset | int | The number of items to ignore for paging purpose
keyword | string | Check for suitable value of text field returned in keywords/list endpoint
lang | string | The language code

## keywords/list

```shell
curl "https://tripadvisor1.p.rapidapi.com/keywords/list?location_id=8014024&limit=10&offset=0" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: tripadvisor1.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to list interesting keywords related to a specific location by its location_id

### HTTP Request

`GET https://tripadvisor1.p.rapidapi.com/keywords/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
location_id | int (required) | The value of location_id field that returned in hotels/list, restaurants/list, or attractions/list endpoints
limit | int | The number of items per response (max 10)
offset | int | The number of items to ignore for paging purpose 

# Morning Star API
## market/v2/auto-complete

```shell
curl "https://morning-star.p.rapidapi.com/market/v2/auto-complete?q=nasdaq" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "count": 34,
    "pages": 6,
    "results": [
        {
            "id": "us_security-0P000003RU",
            "name": "Nasdaq Inc",
            "description": null,
            "exchange": "XNAS",
            "performanceId": "0P000003RU",
            "securityType": "ST",
            "ticker": "NDAQ",
            "type": "us_security",
            "url": null
        },
        ...
    ]
}
```

This endpoint is used to get auto suggestion by word or phase

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/v2/auto-complete`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
q | string (required) | Any thing you are familiar with, stock, index, organization, etc...

## market/auto-complete

curl "https://morning-star.p.rapidapi.com/market/auto-complete?query=nasdaq" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "Name": "Nasdaq Inc",
        "Currency": "USD",
        "Exchange": "XNAS",
        "Type": "ST",
        "TypeName": "Stock",
        "ExchangeShortName": "NASDAQ",
        "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
        "CompanyId": "0C000008J5",
        "PerformanceId": "0P000003RU",
        "ShareClassId": "0P000003RU",
        "FundShareClassId": "0P000003RU",
        "InceptionDate": "2002-07-01",
        "Sector": "Financial Services",
        "Industry": "Financial Data & Stock Exchanges",
        "RegionAndTicker": "USA:NDAQ",
        "Instrument": "126.1.NDAQ"
    },
    ...
]
```

This endpoint is used to get auto complete suggestion for stocks

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/auto-complete`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
query | string (required) | The query value to get auto complete suggestions

## market/v2/get-movers

```shell
curl "https://morning-star.p.rapidapi.com/market/v2/get-movers" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "actives": [
        {
            "exchange": "XNAS",
            "lastPrice": 8.82,
            "percentChange": 20.0,
            "performanceId": "0P0001LH7T",
            "priceChange": 1.47,
            "standardName": "Clover Health Investments Corp Ordinary Shares - Class A",
            "ticker": "CLOV",
            "volume": 2.46288816E8
        },
        ...
    ],
    "gainers": [
        {
            "exchange": "XNAS",
            "lastPrice": 31.3,
            "percentChange": 73.8889,
            "performanceId": "0P0001M4F7",
            "priceChange": 13.3,
            "standardName": "Recursion Pharmaceuticals Inc Class A",
            "ticker": "RXRX",
            "volume": 5653785.0
        },
        ...
    ],
    "losers": [
        {
            "exchange": "XNAS",
            "lastPrice": 34.67,
            "percentChange": -15.3978,
            "performanceId": "0P00017C7L",
            "priceChange": -6.31,
            "standardName": "Editas Medicine Inc",
            "ticker": "EDIT",
            "volume": 6752792.0
        },
        ..
    ]
}
```

This endpoint is used to get movers, such as : actives, gainers, losers,  etc...

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/v2/get-movers`

## market/get-movers

curl "https://morning-star.p.rapidapi.com/market/get-movers?PerformanceId=0P00001GJH" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "Top10": {
        "Actives": {
            "Label": "Most Active",
            "Securities": [
                {
                    "Security": {
                        "Name": "Clover Health Investments Corp Ordinary Shares - Class A",
                        "Currency": "USD",
                        "Exchange": "XNAS",
                        "Type": "ST",
                        "TypeName": "Stock",
                        "ExchangeShortName": "NASDAQ",
                        "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
                        "CompanyId": "0C0000C1E4",
                        "PerformanceId": "0P0001LH7T",
                        "ShareClassId": "0P0001LH7T",
                        "FundShareClassId": "0P0001LH7T",
                        "Sector": "Healthcare",
                        "Industry": "Healthcare Plans",
                        "RequestKey": "126.1.CLOV",
                        "Detail": {
                            "StarRating": 3,
                            "IsStarRatingBasedOnExtendedPerformance": false,
                            "CreditRating": "Premium",
                            "RevenueTTM": 0,
                            "PriceProspectiveEarnings": -17.6056,
                            "PriceBook": 4.516285,
                            "ReturnOnInvestmentCapital": -1.73,
                            "ReturnOnAssets": {
                                "FinancialYear1": -1.57
                            },
                            "ReturnOnEquity": {
                                "FinancialYear1": -1.7
                            },
                            "EarningsPerShare": {
                                "TrailingTwelveMonths": -0.0167,
                                "FinancialYear1": -0.0167
                            },
                            "OperatingMargin": {},
                            "NetMargin": {},
                            "FreeCashFlowMargin": {},
                            "QuarterlyEarningsPerShare": {
                                "TrailingTwelveMonths": -0.0167,
                                "Quarter1": 0
                            },
                            "Valuation": {
                                "AnalystCoverageStatus": "COVERED",
                                "BestRatingType": "Premium",
                                "PriceFairValue": {
                                    "StarRating34": "Premium",
                                    "StarRating45": "Premium",
                                    "StarRating12": "Premium",
                                    "StarRating23": "Premium"
                                },
                                "Take": {
                                    "FairValue": "Premium",
                                    "Assessment": "Premium",
                                    "FairValueUncertainty": "Premium",
                                    "PremiumDiscountCurrent": "Premium",
                                    "PremiumDiscountValue": "Premium",
                                    "EconomicMoat": "Premium"
                                }
                            },
                            "BestRatingType": "Quan",
                            "FairValue": 9.12093,
                            "Assessment": "Fairly Valued"
                        },
                        "RegionAndTicker": "USA:CLOV",
                        "Instrument": "126.1.CLOV"
                    },
                    "Quote": {
                        "Price": 8.82,
                        "PriceChange": 1.47,
                        "PercentChange": 20.0,
                        "OpenPrice": 7.36,
                        "Volume": 7590180,
                        "AverageVolume": 230080,
                        "YesterdayPrice": 7.35,
                        "DayHigh": 10.03,
                        "DayLow": 7.23,
                        "FiftyTwoWeekHigh": 17.45,
                        "FiftyTwoWeekLow": 6.31,
                        "Currency": "USD",
                        "ActivityTimeUTC": "2021-04-16T12:36:59Z",
                        "ExchangeActivityTimeLabel": "04/16/2021 08:36 AM EDT",
                        "MarketPhase": "Premarket",
                        "Bid": 9.48,
                        "Ask": 9.49,
                        "MarketCapInMillions": 3868.12058024,
                        "Yield": null,
                        "PriceToEarningRatio": null,
                        "PremiumDiscount": null
                    }
                },
                ...
            ]
        },
        "Gainers": {
            "Label": "Gainers",
            "Securities": [
                {
                    "Security": {
                        "Name": "Recursion Pharmaceuticals Inc Class A",
                        "Currency": "USD",
                        "Exchange": "XNAS",
                        "Type": "ST",
                        "TypeName": "Stock",
                        "ExchangeShortName": "NASDAQ",
                        "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
                        "CompanyId": "0C0000C3E9",
                        "PerformanceId": "0P0001M4F7",
                        "ShareClassId": "0P0001M4F7",
                        "FundShareClassId": "0P0001M4F7",
                        "Sector": "Healthcare",
                        "Industry": "Biotechnology",
                        "RequestKey": "126.1.RXRX",
                        "Detail": {
                            "IsStarRatingBasedOnExtendedPerformance": false,
                            "RevenueTTM": 3.962,
                            "PriceSales": 888.487567,
                            "ReturnOnAssets": {
                                "FinancialYear1": -43.5,
                                "FinancialYear2": -61.01
                            },
                            "ReturnOnEquity": {},
                            "EarningsPerShare": {
                                "TrailingTwelveMonths": -0.77,
                                "FinancialYear1": -0.77,
                                "FinancialYear2": -0.5502
                            },
                            "OperatingMargin": {
                                "TrailingTwelveMonths": -2135.66,
                                "FinancialYear1": -2135.66,
                                "FinancialYear2": -2692.58
                            },
                            "NetMargin": {
                                "FinancialYear1": -2196.01,
                                "FinancialYear2": -2668.35
                            },
                            "FreeCashFlowMargin": {},
                            "QuarterlyEarningsPerShare": {
                                "TrailingTwelveMonths": -0.77
                            },
                            "Valuation": {
                                "AnalystCoverageStatus": "NOT_COVERED"
                            }
                        },
                        "RegionAndTicker": "USA:RXRX",
                        "Instrument": "126.1.RXRX"
                    },
                    "Quote": {
                        "Price": 31.3,
                        "PriceChange": 13.3,
                        "PercentChange": 73.8889,
                        "OpenPrice": 30.0,
                        "Volume": 4781,
                        "AverageVolume": 27116,
                        "YesterdayPrice": 18.0,
                        "DayHigh": 33.0,
                        "DayLow": 25.17,
                        "FiftyTwoWeekHigh": 33.0,
                        "FiftyTwoWeekLow": 25.17,
                        "Currency": "USD",
                        "ActivityTimeUTC": "2021-04-16T12:35:40Z",
                        "ExchangeActivityTimeLabel": "04/16/2021 08:35 AM EDT",
                        "MarketPhase": "Premarket",
                        "Bid": 28.75,
                        "Ask": 29.5,
                        "MarketCapInMillions": 4653.4596573,
                        "Yield": null,
                        "PriceToEarningRatio": null,
                        "PremiumDiscount": null
                    }
                },
                ...
            ]
        },
        "Losers": {
            "Label": "Losers",
            "Securities": [
                {
                    "Security": {
                        "Name": "Editas Medicine Inc",
                        "Currency": "USD",
                        "Exchange": "XNAS",
                        "Type": "ST",
                        "TypeName": "Stock",
                        "ExchangeShortName": "NASDAQ",
                        "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
                        "CompanyId": "0C0000B1VW",
                        "PerformanceId": "0P00017C7L",
                        "ShareClassId": "0P00017C7L",
                        "FundShareClassId": "0P00017C7L",
                        "InceptionDate": "2016-02-03",
                        "Sector": "Healthcare",
                        "Industry": "Biotechnology",
                        "RequestKey": "126.1.EDIT",
                        "Detail": {
                            "StarRating": 3,
                            "EquityStyle": 9,
                            "IsStarRatingBasedOnExtendedPerformance": false,
                            "CreditRating": "Premium",
                            "RevenueTTM": 90.732,
                            "PriceProspectiveEarnings": -10.4493,
                            "PriceBook": 5.933819,
                            "PriceSales": 22.395489,
                            "ReturnOnInvestmentCapital": -33.34,
                            "ReturnOnAssets": {
                                "TrailingTwelveMonths": -21.44750,
                                "FinancialYear1": -21.45,
                                "FinancialYear2": -28.79,
                                "FinancialYear3": -27.71,
                                "FinancialYear4": -39.95,
                                "FinancialYear5": -51.37
                            },
                            "ReturnOnEquity": {
                                "TrailingTwelveMonths": -35.35730,
                                "FinancialYear1": -35.36,
                                "FinancialYear2": -53.65,
                                "FinancialYear3": -49.5,
                                "FinancialYear4": -70.22,
                                "FinancialYear5": -377.64
                            },
                            "EarningsPerShare": {
                                "TrailingTwelveMonths": -1.98,
                                "FinancialYear1": -1.98,
                                "FinancialYear2": -2.68,
                                "FinancialYear3": -2.33,
                                "FinancialYear4": -2.98,
                                "FinancialYear5": -3.02
                            },
                            "OperatingMargin": {
                                "TrailingTwelveMonths": -148.61,
                                "FinancialYear1": -148.61,
                                "FinancialYear2": -686.39,
                                "FinancialYear3": -356.1,
                                "FinancialYear4": -873.64,
                                "FinancialYear5": -1605.62
                            },
                            "NetMargin": {
                                "TrailingTwelveMonths": -127.8226,
                                "FinancialYear1": -127.82,
                                "FinancialYear2": -651.43,
                                "FinancialYear3": -344.28,
                                "FinancialYear4": -876.49,
                                "FinancialYear5": -1606.31
                            },
                            "FreeCashFlowMargin": {},
                            "QuarterlyEarningsPerShare": {
                                "TrailingTwelveMonths": -1.98,
                                "Quarter1": -1,
                                "Quarter2": 0.12,
                                "Quarter3": -0.43,
                                "Quarter4": -0.69
                            },
                            "Valuation": {
                                "AnalystCoverageStatus": "COVERED",
                                "BestRatingType": "Premium",
                                "PriceFairValue": {
                                    "StarRating34": "Premium",
                                    "StarRating45": "Premium",
                                    "StarRating12": "Premium",
                                    "StarRating23": "Premium"
                                },
                                "Take": {
                                    "FairValue": "Premium",
                                    "CompanyMediumProfile": "Editas Medicine Inc is a genome editing company which is engaged in treating patients with genetically defined diseases by correcting disease-causing genes.",
                                    "Assessment": "Premium",
                                    "FairValueUncertainty": "Premium",
                                    "PremiumDiscountCurrent": "Premium",
                                    "PremiumDiscountValue": "Premium",
                                    "EconomicMoat": "Premium"
                                }
                            },
                            "BestRatingType": "Quan",
                            "FairValue": 41.4514,
                            "Assessment": "Undervalued"
                        },
                        "RegionAndTicker": "USA:EDIT",
                        "Instrument": "126.1.EDIT"
                    },
                    "Quote": {
                        "Price": 34.67,
                        "PriceChange": -6.31,
                        "PercentChange": -15.3978,
                        "OpenPrice": 38.27,
                        "Volume": 8706,
                        "AverageVolume": 7856,
                        "YesterdayPrice": 40.98,
                        "DayHigh": 39.22,
                        "DayLow": 33.5828,
                        "FiftyTwoWeekHigh": 99.95,
                        "FiftyTwoWeekLow": 21.41,
                        "Currency": "USD",
                        "ActivityTimeUTC": "2021-04-16T12:36:23Z",
                        "ExchangeActivityTimeLabel": "04/16/2021 08:36 AM EDT",
                        "MarketPhase": "Premarket",
                        "Bid": 34.02,
                        "Ask": 34.13,
                        "MarketCapInMillions": 2292.35577773,
                        "Yield": null,
                        "PriceToEarningRatio": null,
                        "PremiumDiscount": null
                    }
                },
                ...
            ]
        }
    },
    "Timestamp": "2021-04-19T12:52:00Z"
}
```

This endpoint is used to get top 10 gainers, losers, actives of specific market

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/get-movers`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
PerformanceId | string (required) | Get value of PerformanceId field from /market/auto-complete and /market/get-summary APIs

## market/v2/get-returns

```shell
curl "https://morning-star.p.rapidapi.com/market/v2/get-returns?performanceIds=0P0000OQN8,0P000000GY" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "0P0000OQN8": {
        "marketReturn5Years": 70.797506,
        "ticker": "TSLA",
        "marketReturn1Year": 537.33779,
        "securityId": "F00000ITT6",
        "exchange": "XNAS",
        "marketReturn3Years": 132.381744
    },
    ...
}
```

This endpoint is used to get market return by years

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/v2/get-returns`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceIds | string (required) | The value of performanceId returned in .../market/v2/get-movers , .../market/v2/auto-complete, etc... endpoints. Separated by comma to query multiple entities.

## market/v2/get-realtime-data

```shell
curl "https://morning-star.p.rapidapi.com/market/v2/get-realtime-data?performanceIds=0P0000OQN8,0P000000GY" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "0P0000OQN8": {
        "netChange": {
            "value": 0.93,
            "filtered": false
        },
        "previousClosePrice": {
            "value": 738.85,
            "filtered": false
        },
        "adjustedClosePrice": {
            "value": 738.85,
            "filtered": false
        },
        "name": {
            "value": "Tesla",
            "filtered": false
        },
        "percentNetChange": {
            "value": 0.1259,
            "filtered": false
        },
        "tradingStatus": {
            "value": "Closed",
            "filtered": false
        },
        "lastPrice": {
            "value": 739.78,
            "filtered": false,
            "date": {
                "value": "2021-04-16T16:15:02-04:00",
                "filtered": false
            }
        }
    },
    ...
}
```

This endpoint is used to query one or more entities data at once

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/v2/get-realtime-data`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceIds | string (required) | The value of performanceId returned in .../market/v2/get-movers , .../market/v2/auto-complete, etc... endpoints. Separated by comma to query multiple entities.

## market/v2/get-time-series

```shell
curl "https://morning-star.p.rapidapi.com/market/v2/get-time-series?0P0000OQN8,0P000000GY" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "0P0000OQN8": [
        {
            "datetime": "2021-04-16T20:00:00Z",
            "volume": 328272,
            "lastPrice": 739.78,
            "openPrice": 739.67,
            "lowPrice": 739.48,
            "highPrice": 739.78
        },
        ...
    ],
    ...
}
```

This endpoint is used to query one or more entities data at once in time series manner

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/v2/get-time-series`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceIds | string (required) | The value of performanceId returned in .../market/v2/get-movers , .../market/v2/auto-complete, etc... endpoints. Separated by comma to query multiple entities.

## market/v2/get-quotes

```shell
curl "https://morning-star.p.rapidapi.com/market/v2/get-quotes?performanceIds=0P000000GY" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "0P000000GY": {
        "name": "Apple Inc",
        "exchange": "XNAS",
        "region": "USA",
        "ticker": "AAPL",
        "price": 134.15,
        "priceChange": -0.35,
        "percentChange": -0.2602,
        "openPrice": 134.3,
        "volume": 84922386,
        "yesterdayPrice": 134.5,
        "dayHigh": 134.67,
        "dayLow": 133.28,
        "fiftyTwoWeekHigh": 145.09,
        "fiftyTwoWeekLow": 66.3575,
        "currency": "USD",
        "marketPhase": "Closed",
        "activityTimeUTC": "2021-04-16T23:59:56Z",
        "exchangeActivityTimeLabel": "04/16/2021 06:41 PM EDT",
        "securityId": "0P000000GY"
    },
	...
}
```

This endpoint is used to query live data for one or multiple quotes at once.

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/v2/get-quotes`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceIds | string (required) | The value of performanceId returned in .../market/v2/get-movers , .../market/v2/auto-complete, etc... endpoints. Separated by comma to query multiple entities.

## market/get-global-indices

```shell
curl "https://morning-star.p.rapidapi.com/market/get-global-indices" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "realTimeLastUpdateDate": "2021-04-19T12:51:19.000Z",
    "gmbIndexDataList": [
        {
            "symbol": "33.10.!MSTAR",
            "ticker": "!MSTAR",
            "exchange": 33,
            "securityType": 10,
            "netChange": 31.95,
            "netChangePer": 0.3011,
            "companyName": "Morningstar U.S. Market Index",
            "marketStatus": "Closed",
            "currency": "USD",
            "avgVolume": 0,
            "volume": 0,
            "recentTradingDayOpenPrice": 10640.54,
            "lastClosePrice": 10610.9,
            "lastPrice": 10642.85,
            "lastUpdateDate": "2021-04-16T22:03:05.000Z",
            "lastUpdateTime": "18:03:05.000",
            "priceReturn1Week": 1.4429832,
            "priceReturn1Month": 5.0235993,
            "realTimeLastUpdateDate": "16-04-2021",
            "realTimeLastUpdateTime": "18:03:06.000",
            "isRunning": false
        },
        ...
    ]
}
```

This endpoint is used to get information of global indices

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/get-global-indices`

## market/get-summary

```shell
curl "https://morning-star.p.rapidapi.com/market/get-summary" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "MarketRegions": {
        "USA": [
            {
                "PerformanceId": "0P00001GJH",
                "RegionAndTicker": "USA:MSTAR",
                "Currency": "USD",
                "Exchange": "SPI",
                "ExchangeShortName": "SPI",
                "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
                "Name": "Morningstar US Market",
                "StarRating": null,
                "Type": "XI",
                "Price": 10642.85,
                "PriceChange": 31.95,
                "PercentChange": 0.3011,
                "OpenPrice": 10640.54,
                "Volume": null,
                "DayHigh": 10657.36,
                "DayLow": 10604.57,
                "ActivityTimeUTC": "2021-04-16T22:03:05Z",
                "ExchangeActivityTimeLabel": "04/16/2021 06:03 PM EDT",
                "AverageVolume": 169.5566,
                "InceptionDate": "2002-07-03",
                "YesterdayPrice": 10610.9
            },
            ...
        ],
        "Europe": [
            {
                "PerformanceId": "0P00001FKQ",
                "RegionAndTicker": null,
                "Currency": "GBP",
                "Exchange": null,
                "ExchangeShortName": null,
                "ExchangeTimeZoneOffsetFromUTCInSeconds": 3600,
                "Name": "FTSE 100",
                "StarRating": null,
                "Type": "XI",
                "Price": 7016.33,
                "PriceChange": -3.2,
                "PercentChange": -0.0456,
                "OpenPrice": 7019.53,
                "Volume": null,
                "DayHigh": 7040.26,
                "DayLow": 7007.45,
                "ActivityTimeUTC": "2021-04-19T12:40:50Z",
                "ExchangeActivityTimeLabel": "04/19/2021 08:40 AM EDT",
                "AverageVolume": null,
                "InceptionDate": "1984-01-03",
                "YesterdayPrice": 7019.53
            },
            ...
        ],
        "Asia": [
            {
                "PerformanceId": "0P00006MR4",
                "RegionAndTicker": "JPN:100000018",
                "Currency": "JPY",
                "Exchange": "XOSE",
                "ExchangeShortName": "XOSE",
                "ExchangeTimeZoneOffsetFromUTCInSeconds": 32400,
                "Name": "Nikkei 225 Average",
                "StarRating": null,
                "Type": "XI",
                "Price": 29685.37,
                "PriceChange": 2.0,
                "PercentChange": 0.0067,
                "OpenPrice": 29688.32,
                "Volume": null,
                "DayHigh": 29808.01,
                "DayLow": 29530.84,
                "ActivityTimeUTC": "2021-04-19T06:00:01Z",
                "ExchangeActivityTimeLabel": "04/19/2021 02:00 AM EDT",
                "AverageVolume": null,
                "InceptionDate": "1950-09-07",
                "YesterdayPrice": 29683.37
            },
            ...
        ],
        "CAN": [
            {
                "PerformanceId": "0P00008IVF",
                "RegionAndTicker": "CAN:0000",
                "Currency": "CAD",
                "Exchange": "XTSE",
                "ExchangeShortName": "XTSE",
                "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
                "Name": "S&P/TSX Composite",
                "StarRating": null,
                "Type": "XI",
                "Price": 19351.32,
                "PriceChange": 29.4,
                "PercentChange": 0.1522,
                "OpenPrice": 19380.68,
                "Volume": 238407251,
                "DayHigh": 19380.68,
                "DayLow": 19293.78,
                "ActivityTimeUTC": "2021-04-16T20:59:23Z",
                "ExchangeActivityTimeLabel": "04/16/2021 04:59 PM EDT",
                "AverageVolume": 217.6816,
                "InceptionDate": "1960-01-29",
                "YesterdayPrice": 19321.92
            },
            ...
        ]
    },
    "Barometers": {
        "ThreeYears": [
            {
                "PercentChange": 10.31756,
                "Level": 2
            },
            ...
        ],
        "OneYear": [
            {
                "PercentChange": 41.08093,
                "Level": 3
            },
			...
        ],
        "ThreeMonths": [
            {
                "PercentChange": 9.74871,
                "Level": 3
            },
            ...
        ],
        "OneWeek": [
            {
                "PercentChange": 0.77931,
                "Level": 2
            },
            ...
        ],
        "OneDay": [
            {
                "PercentChange": 0.6279,
                "Level": 2
            },
            ...
        ],
        "OneMonth": [
            {
                "PercentChange": 3.01136,
                "Level": 2
            },
            ...
        ]
    },
    "Timestamp": "2021-04-19T12:55:52Z"
}
```

This endpoint is used to query live summary information of the markey at the request time

### HTTP Request

`GET https://morning-star.p.rapidapi.com/market/get-summary`

## stock/v2/get-realtime-data

```shell
curl "https://morning-star.p.rapidapi.com/stock/v2/get-realtime-data?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "status": "OK",
    "lastPrice": 739.78,
    "bid": 739.1,
    "bidSize": 15,
    "ask": 739.25,
    "askSize": 41,
    "lotSize": 100,
    "volume": 27979526,
    "recentTradingDayOpenPrice": 728.65,
    "dayRangeHigh": 749.41,
    "dayRangeLow": 724.6,
    "lastClose": 738.85,
    "priceOfTradeAfter": 739.25,
    "timeOfTradeAfter": "2021-04-16T20:14:56.000",
    "recentTradingDay": "2021-04-16",
    "lastUpdateTime": "2021-04-16T16:15:02.000",
    "recentTradingDayJulian": "16-04-2021",
    "tradingStatus": "Closed",
    "marketCap": 710080425189.1199951172,
    "dividendYield": null,
    "yearRangeHigh": 900.4,
    "yearRangeLow": 134.758,
    "currencyCode": "USD",
    "currencySymbol": "$",
    "listedCurrency": "USD",
    "tradedCurrency": null,
    "avgVolume": 94717.2741935484,
    "exchangeID": "XNAS",
    "exchangeName": "NASDAQ",
    "exchangeTimeZone": "EST",
    "type": "Equity",
    "ts": "1618622172000",
    "dayChange": 0.93,
    "dayChangePer": 0.1259,
    "bidMarket": "16",
    "askMarket": "16",
    "originationMarket": "18",
    "message": "126.1.TSLA",
    "lastUpdateRealTimeDate": "16-04-2021",
    "lastUpdateRealTimeTime": "21:16:12.000",
    "nav": null,
    "oneDayReturn": null,
    "navLastDate": null,
    "navLastDate1": null,
    "navLastTime": null,
    "isBats": true
}
```

This endpoint is used to get detail information of stock, market

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-realtime-data`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | The value of performanceId returned in .../market/v2/get-movers , .../market/v2/auto-complete, etc... endpoints. 

## stock/v2/get-mini-chart-realtime-data

```shell
curl "https://morning-star.p.rapidapi.com/stock/v2/get-mini-chart-realtime-data?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "iiv": null,
    "status": "OK",
    "idsMessage": "126.1.TSLA",
    "lastPrice": 739.78,
    "priceOfTradeAfter": 739.25,
    "timeOfTradeAfter": "2021-04-16T20:14:56.000",
    "lastUpdateTime": "2021-04-16T16:15:02.000",
    "tradingStatus": "Closed",
    "dayChange": 0.93,
    "dayChangePer": 0.1259,
    "lastClose": 738.85,
    "exchangeId": "XNAS",
    "ts": "1618622172000",
    "currencyCode": "USD"
}
```

This endpoint is used to draw chart in Quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-mini-chart-realtime-data`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | The value of performanceId returned in .../market/v2/get-movers , .../market/v2/auto-complete, etc... endpoints. 
 
## stock/v2/get-security-info

curl "https://morning-star.p.rapidapi.com/stock/v2/get-security-info?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "userType": "Free",
    "performanceId": "0P0000OQN8",
    "securityName": "Tesla Inc",
    "ticker": "TSLA",
    "starRating": "_PO_",
    "qualRating": "_PO_",
    "quantRating": "_PO_",
    "bestRatingType": "Qual",
    "investmentStyle": "3",
    "priceEarnings": "1155.906250",
    "priceBook": "31.949625",
    "priceSale": "25.405306",
    "forwardPE": "175.43859649122805",
    "forwardDivYield": null,
    "starRatingDate": "2021-04-16T21:19:00Z",
    "returnStatistics": {
        "numberOfMonths": 60.0,
        "beta": 2.016234
    }
}
```

This endpoint is mapped to quote section in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-security-info`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-price-fair-value

curl "https://morning-star.p.rapidapi.com/stock/v2/get-price-fair-value?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "_meta": {
        "responseStatus": "200700",
        "hint": "Securities successfully returned",
        "performanceId": "0P0000OQN8"
    },
    "columnDefs": [
        "2011",
        "2012",
        "2013",
        "2014",
        "2015",
        "2016",
        "2017",
        "2018",
        "2019",
        "2020",
        "YTD"
    ],
    "chart": {
        "chartDatums": {
            "recent": {
                "latestFairValue": "_PO_",
                "uncertainty": "_PO_",
                "latestClose": "739.78",
                "bf": [
                    "2021-04-18",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_"
                ]
            },
            "yearly": [
                {
                    "annualHigh": "7",
                    "annualLow": "4.2219999999999995",
                    "monthly": [
                        {
                            "high": "5.742",
                            "low": "4.474",
                            "close": "4.82",
                            "starRating": null,
                            "bf": [
                                "2011-01-31",
                                "_PO_",
                                "_PO_",
                                "_PO_",
                                "_PO_",
                                "_PO_"
                            ]
                        },
                        ..
                    ]
                },
                ...
            ]
        },
        "isQual": true,
        "closePriceCurrency": null,
        "realtimeCurrency": "USD",
        "lastCloseCurrency": "USD",
        "fairValCurrency": "USD"
    },
    "table": {
        "rows": [
            {
                "label": "Price/Fair Value",
                "salDataId": "price.fair.value.label",
                "isQuantitative": false,
                "datum": [
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_",
                    "_PO_"
                ]
            },
            ...
        ]
    },
    "userType": "Free",
    "footer": {
        "asOfLabel": "As of",
        "asOfDate": "2021-04-16T00:00:00.000",
        "indexLabel": "Index:",
        "indexName": "Morningstar US Market TR USD"
    }
}
```

This endpoint is used to mapped to price vs fair value  tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-price-fair-value`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-key-stats

curl "https://morning-star.p.rapidapi.com/stock/v2/get-key-stats?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "revenue3YearGrowth": {
        "stockValue": "38.9400",
        "indAvg": "-3.2700"
    },
    "netIncome3YearGrowth": {
        "stockValue": null,
        "indAvg": "-13.4000"
    },
    "operatingMarginTTM": {
        "stockValue": "6.3200",
        "indAvg": "5.3200"
    },
    "netMarginTTM": {
        "stockValue": "2.1900",
        "indAvg": "3.2800"
    },
    "roaTTM": {
        "stockValue": "1.6000",
        "indAvg": "1.7900"
    },
    "roeTTM": {
        "stockValue": "4.7800",
        "indAvg": "6.2700"
    },
    "debitToEquity": {
        "stockValue": "0.4887",
        "indAvg": "0.8739"
    },
    "freeCashFlow": {
        "cashFlowTTM": "2701000000",
        "date": "2020-12-31T06:00:00.000"
    }
}
```

This endpoint is used to mapped to key ratios section in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-key-stats`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-analysis-report

curl "https://morning-star.p.rapidapi.com/stock/v2/get-analysis-report?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "userType": "Free",
    "total": 110,
    "rpsCovered": true,
    "isLocalized": true,
    "analysisReport": {
        "headLine": "Tesla Continues Its Aggressive Growth Plans",
        "investmentThesis": "Tesla has a chance to be the dominant electric vehicle firm long term and is a leading autonomous vehicle player as well as a vertically integrated sustainable energy company with energy generation and storage products, but we see immense competition coming this decade. Tesla's product plans for now do not mean an electric vehicle for every consume",
        "investmentThesisDateUTC": "2021-02-24T00:43:00Z",
        "economicMoat": null,
        "economicMoatDateUTC": "2021-02-24T00:43:00Z",
        "valuation": null,
        "valuationDateUTC": "2021-02-24T01:43:00Z",
        "risk": null,
        "riskDateUTC": "2021-02-24T00:43:00Z",
        "management": null,
        "managementDateUTC": "2021-02-24T01:43:00Z",
        "bullsSay": null,
        "bearsSay": null,
        "author": {
            "authorId": 766,
            "authorName": "David Whiston",
            "authorImage": "https://im.mstar.com/Content/CMSImages/78x78/766-dwhisto-78x78.jpg",
            "authorImageHeadshot": "https://im.mstar.com/im/BetaSiteHeadshots/David-Whiston_766.jpg",
            "email": "david.whiston@morningstar.com",
            "phoneNumber": "+1 312 384 5442",
            "holdings": "AMZN BP DIS EXPR GOOG GOOGL IPI MELI MOAT AAPL AMAT ECPN FB GLW JNJ MSFT SYK",
            "jobTitle": null,
            "isPrimaryAuthor": true,
            "profiles": [
                {
                    "byLine": "David Whiston",
                    "isPrimaryProfile": true,
                    "jobTitle": "Sector Strategist",
                    "language": "en-US"
                }
            ]
        }
    },
    "analystNote": {
        "note": null,
        "title": null,
        "date": null,
        "author": null
    },
    "lastUpdateBy": 766
}
```

This endpoint is used to get detail information of stock, market

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-analysis-report`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-trailing-total-returns

curl "https://morning-star.p.rapidapi.com/stock/v2/get-trailing-total-returns?performanceId=0P0000OQN8&dataType=d" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "returnDate": "2021-04-16T05:00:00.000",
    "trailingTotalReturnsList": [
        {
            "name": "TSLA",
            "trailing1DayReturn": "0.12587",
            "trailing1WeekReturn": "9.27004",
            "trailing1MonthReturn": "9.29264",
            "trailing3MonthReturn": "-10.45560",
            "trailing6MonthReturn": "68.25801",
            "trailingYearToDateReturn": "4.83370",
            "trailing1YearReturn": "396.35673",
            "trailing3YearReturn": "133.32186",
            "trailing5YearReturn": "70.79437",
            "trailing10YearReturn": "64.44369",
            "trailing15YearReturn": null
        },
        ...
    ]
}
```

This endpoint is used to mapped to trailing returns  tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-trailing-total-returns`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints
dataType | string | One of the following : d - day &#124; m - month &#124; q - quarterly

## stock/v2/get-analysis-data

curl "https://morning-star.p.rapidapi.com/stock/v2/get-analysis-data?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "ticker": "TSLA",
    "isQuan": false,
    "userType": "Free",
    "valuation": {
        "fairValue": "_PO_",
        "fairValueDate": "2021-02-24T00:00:00.000",
        "assessment": "_PO_",
        "assessmentDate": "2021-04-18T00:00:00.000",
        "uncertainty": "_PO_",
        "moat": "_PO_",
        "moatDate": "2021-04-18T00:00:00.000",
        "moatTrendEvaluate": "Positive",
        "premiumDisc": "_PO_",
        "stewardship": "_PO_",
        "stewardshipDate": "2021-04-18T00:00:00.000",
        "premDiscDelta": "_PO_",
        "oneStar": "_PO_",
        "oneStarDate": "2021-04-18T00:00:00.000",
        "fiveStar": "_PO_",
        "fiveStarDate": "2021-04-18T00:00:00.000",
        "fairValCurrency": "USD",
        "bf2": "_PO_",
        "bf3": "_PO_",
        "bf4": "_PO_",
        "bf5": "_PO_",
        "lastClose": "_PO_",
        "startRating": "_PO_",
        "lastCloseCurrency": "USD"
    },
    "companyProfile": "Founded in 2003 and based in Palo Alto, California, Tesla is a vertically integrated sustainable energy company that also aims to transition the world to electric mobility by making electric vehicles. It sells solar panels and solar roofs for energy generation plus batteries for stationary storage for residential and commercial properties including utilities. It also makes solar roofs and plans to enter the HVAC market. The Tesla Roadster debuted in 2008, Model S in 2012, Model X in 2015, Model 3 in 2017, and Model Y in 2020. Global deliveries in 2020 were 499,647 units. Tesla went public in 2010 and employs about 71,000 people."
}
```

This endpoint is used to mapped to analysis section in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-analysis-data`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-financials

curl "https://morning-star.p.rapidapi.com/stock/v2/get-financials?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "incomeStatement": {
        "_meta": {
            "companyId": "0C00004EP4",
            "statementType": "income-statement",
            "periodReport": "Success",
            "latestReport": "Success"
        },
        "columnDefs": [
            "2018",
            "2019",
            "2020",
            "TTM"
        ],
        "filingIdList": [
            "211708709",
            "264149200",
            "320461313",
            null
        ],
        "columnDefs_labels": [
            "20181231",
            "20191231",
            "20201231",
            "20201231"
        ],
        "rows": [
            {
                "label": "Total Revenue",
                "dataPointId": "IFIS001170",
                "datum": [
                    21.46,
                    24.58,
                    31.54,
                    31.54
                ]
            },
            ...
        ],
        "footer": {
            "currency": "USD",
            "currencySymbol": "$",
            "orderOfMagnitude": "Billion",
            "fiscalYearEndDate": "12-31"
        }
    },
    "balanceSheet": {
        "_meta": {
            "companyId": "0C00004EP4",
            "statementType": "balance-sheet",
            "periodReport": "Success",
            "latestReport": "Success"
        },
        "columnDefs": [
            "2018",
            "2019",
            "2020",
            "Q3 2020"
        ],
        "filingIdList": [
            null,
            null,
            "320461313",
            "305166809"
        ],
        "columnDefs_labels": [
            "",
            "",
            "20201231",
            "20230930"
        ],
        "rows": [
            {
                "label": "Total Assets",
                "dataPointId": "IFBS002270",
                "datum": [
                    null,
                    null,
                    52.15,
                    45.69
                ]
            },
            ...
        ],
        "footer": {
            "currency": "USD",
            "currencySymbol": "$",
            "orderOfMagnitude": "Billion",
            "fiscalYearEndDate": "12-31"
        }
    },
    "cashFlow": {
        "_meta": {
            "companyId": "0C00004EP4",
            "statementType": "cash-flow",
            "periodReport": "Success",
            "latestReport": "Success"
        },
        "columnDefs": [
            "2018",
            "2019",
            "2020",
            "TTM"
        ],
        "filingIdList": [
            "211708709",
            "264149200",
            "320461313",
            null
        ],
        "columnDefs_labels": [
            "20181231",
            "20191231",
            "20201231",
            "20201231"
        ],
        "rows": [
            {
                "label": "Cash Flow from Operating Activities, Indirect",
                "dataPointId": "IFCF000150",
                "datum": [
                    2.10,
                    2.41,
                    5.94,
                    5.94
                ]
            },
            ...
        ],
        "footer": {
            "currency": "USD",
            "currencySymbol": "$",
            "orderOfMagnitude": "Billion",
            "fiscalYearEndDate": "12-31"
        }
    }
}
```

This endpoint is used to mapped to financials  tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-financials`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints
interval | string | One of the following : quarterly &#124; annual
reportType | string | One of the following : R - Restated &#124; A - As originally reported

## stock/v2/get-splits

curl "https://morning-star.p.rapidapi.com/stock/v2/get-splits?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "splitHistory": [
        {
            "date": "2020-08-31T05:00:00.000",
            "ratio": "5:1"
        }
    ],
    "splitOffHistory": []
}
```

This endpoint is used to mapped to dividends tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-splits`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-executive

curl "https://morning-star.p.rapidapi.com/stock/v2/get-executive?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "rows": [
        {
            "type": "person",
            "personId": "PS00005ROA",
            "name": "Elon Musk",
            "title": "Chief Executive Officer and Director",
            "holding": "75.0000",
            "memberSince": "2008",
            "age": "48",
            "totalCompensation": [
                "37584.00",
                "45936.00",
                "49920.00",
                "2284044884.00",
                "23760.00"
            ],
            "compensation": [
                {
                    "nameId": "salary",
                    "name": "Salary",
                    "datum": [
                        "37584.00",
                        "45936.00",
                        "49920.00",
                        "56380.00",
                        "23760.00"
                    ]
                },
                ...
            ]
        },
        ...
    ],
    "datesDef": [
        "2015",
        "2016",
        "2017",
        "2018",
        "2019"
    ],
    "currency": "USD"
}
```

This endpoint is used to mapped to executive tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-executive`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints
executive | string | One of the following : keyExecutives &#124; boardOfDirectors &#124; committees &#124; transactionHistory &#124; transactionChart 

## stock/v2/get-competitors

curl "https://morning-star.p.rapidapi.com/stock/v2/get-competitors?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "userType": "Free",
    "main": {
        "ticker": "TSLA",
        "name": "Tesla Inc",
        "instrumentId": "126.1.TSLA",
        "fairValue": "_PO_",
        "moat": "_PO_",
        "assessment": "_PO_",
        "starRating": "_PO_",
        "priceSale": "25.405306",
        "priceBook": "31.949625",
        "priceEarnings": "1155.906250",
        "priceFair": "_PO_",
        "isQuant": false,
        "exchangeId": null,
        "shareClassId": null,
        "securityType": null,
        "dividendYield": null,
        "investmentStyle": "3",
        "bf2": "610.75",
        "bf3": "436.25000",
        "bf4": "279.20000",
        "bf5": "174.5",
        "premiumDisc": "112",
        "performanceId": "0P0000OQN8",
        "uncertaintyCurrent": "_PO_",
        "fairValCurrency": "USD",
        "analyst": "David Whiston, Sector Strategist",
        "fairValDate": "2021-02-24T01:40:32Z",
        "starRatingDate": "2021-04-16T21:19:00Z",
        "lastCloseDB": 739.78,
        "lastCloseCurrencyDB": "USD"
    },
    "competitors": [
        {
            "ticker": "F",
            "name": "Ford Motor Co",
            "instrumentId": "126.1.F",
            "fairValue": "_PO_",
            "moat": "_PO_",
            "assessment": "_PO_",
            "starRating": "_PO_",
            "priceSale": "0.382163",
            "priceBook": "1.590497",
            "priceEarnings": "29.829268",
            "priceFair": "_PO_",
            "isQuant": false,
            "exchangeId": null,
            "shareClassId": null,
            "securityType": null,
            "dividendYield": "0.0112",
            "investmentStyle": "1",
            "bf2": "26.25",
            "bf3": "18.75000",
            "bf4": "12.00000",
            "bf5": "7.5",
            "premiumDisc": "-18",
            "performanceId": "0P0000029A",
            "uncertaintyCurrent": "_PO_",
            "fairValCurrency": "USD",
            "analyst": "David Whiston, Sector Strategist",
            "fairValDate": "2021-02-13T00:10:32Z",
            "starRatingDate": "2021-04-16T21:19:00Z",
            "lastCloseDB": 12.23,
            "lastCloseCurrencyDB": "USD"
        },
        ...
    ]
}
```

This endpoint is used to mapped to competitors section in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-competitors`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-mini-chart-quote

curl "https://morning-star.p.rapidapi.com/stock/v2/get-mini-chart-quote?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "status": "OK",
    "idsMessage": "126.1.TSLA",
    "exchangeID": "XNAS",
    "exchangeTimeZoneCode": "EST",
    "exchangeTimeZoneOffset": "-4:00",
    "previousTradingDayClosePrice": 738.85,
    "recentTradingDay": "2021-04-16",
    "lastUpdateDay": "2021-04-16",
    "recentTradingDayOpenTime": "2021-04-16T13:30Z",
    "recentTradingDayCloseTime": "2021-04-16T20:00Z",
    "recentTradingDayOpenPrice": 728.65,
    "exchangeName": "NASDAQ",
    "priceOfTradeAfter": 739.25,
    "tradingStatus": "Pre-Open",
    "recentTradingDayTSPrices": [
        {
            "dateGMT": "16-04-2021",
            "exchangeTime": "20:00",
            "openPrice": 739.67,
            "tradingVolume": 328272,
            "gmtDateTime": "2021-04-16T20:00Z"
        },
        ...
    ],
    "chartStatus": "OK",
    "marketOpenToday": true
}
```

This endpoint is used to used to draw chart in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-mini-chart-quote`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-profile

curl "https://morning-star.p.rapidapi.com/stock/v2/get-profile?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "0P0000OQN8": {
        "ticker": {
            "value": "TSLA",
            "filtered": false
        },
        "website": {
            "value": "https://www.tesla.com",
            "filtered": false
        },
        "headquarterCountry": {
            "value": "United States",
            "filtered": false
        },
        "stockType": {
            "value": "Cyclical",
            "filtered": false
        },
        "headquarterAddress1": {
            "value": "3500 Deer Creek Road",
            "filtered": false
        },
        "industry": {
            "value": "Auto Manufacturers",
            "filtered": false
        },
        "stockStarRating": {
            "value": "8",
            "filtered": true,
            "date": {
                "value": "2021-04-16",
                "filtered": false
            },
            "text": {
                "value": "Significantly Overvalued",
                "filtered": false
            },
            "type": {
                "value": "Qual",
                "filtered": false
            }
        },
        "fiscalYearEndDate": {
            "value": "2021-12-31",
            "filtered": false
        },
        "headquarterCity": {
            "value": "Palo Alto",
            "filtered": false
        },
        "headquarterState": {
            "value": "CA",
            "filtered": false
        },
        "reportDate": {
            "value": "2020-12-31",
            "filtered": false
        },
        "phone": {
            "value": "+1 650 681-5000",
            "filtered": false
        },
        "universe": {
            "value": "EQ",
            "filtered": false
        },
        "headquarterPostalCode": {
            "value": "94304",
            "filtered": false
        },
        "exchange": {
            "value": "XNAS",
            "filtered": false
        },
        "companyProfile": {
            "value": "Founded in 2003 and based in Palo Alto, California, Tesla is a vertically integrated sustainable energy company that also aims to transition the world to electric mobility by making electric vehicles. It sells solar panels and solar roofs for energy generation plus batteries for stationary storage for residential and commercial properties including utilities. It also makes solar roofs and plans to enter the HVAC market. The Tesla Roadster debuted in 2008, Model S in 2012, Model X in 2015, Model 3 in 2017, and Model Y in 2020. Global deliveries in 2020 were 499,647 units. Tesla went public in 2010 and employs about 71,000 people.",
            "filtered": false
        },
        "fax": {
            "value": "+1 650 681-5101",
            "filtered": false
        },
        "totalEmployees": {
            "value": 70757,
            "filtered": false
        },
        "sector": {
            "value": "Consumer Cyclical",
            "filtered": false
        }
    }
}
```

This endpoint is used to mapped to company profile section in quote  tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-profile`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-ownership

curl "https://morning-star.p.rapidapi.com/stock/v2/get-ownership?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "isRestricted": false,
    "userType": "Free",
    "country": "USA",
    "rows": [
        {
            "secId": "FOUSA02W9R",
            "name": "Baron Partners Retail",
            "totalSharesHeld": 0.4349622085663606,
            "totalAssets": 41.53428,
            "currentShares": 4175000,
            "changeAmount": -400000,
            "changePercentage": -8.743169398907105,
            "date": "2021-03-31T00:00:00.000",
            "trend": "_PO_",
            "starRating": "5"
        },
        ...
    ],
    "columnDefs": [
        {
            "columnId": "name",
            "dataType": "string"
        },
        ...
    ]
}
```

This endpoint is used to mapped to ownership tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-ownership`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints
ownership | string | One of the following : OwnershipData &#124; ConcentratedOwners &#124; Sellers &#124; Buyers
asset | string | One of the following : mutualfund &#124; institution

## stock/v2/get-valuation

curl "https://morning-star.p.rapidapi.com/stock/v2/get-valuation?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "Collapsed": {
        "rows": [
            {
                "label": "Price/Sales",
                "salDataId": "price.sales.label",
                "isQuantitative": false,
                "datum": [
                    "13.9084",
                    "8.7982",
                    "10.3395",
                    "9.6434",
                    "8.0332",
                    "4.9809",
                    "4.7027",
                    "3.2209",
                    "2.9983",
                    "25.4896",
                    "25.4053",
                    "6.7559",
                    "2.9495"
                ],
                "subLevel": ""
            },
            ...
        ],
        "columnDefs": [
            "Calendar",
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "Current",
            "5-Yr",
            "Index"
        ],
        "columnDefs_labels": [
            "tabular.data.label.column.year",
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "valuation.headers.current",
            "valuation.headers.fiveyear",
            "valuation.headers.index"
        ],
        "userType": null,
        "footer": {
            "asOfLabel": "As of",
            "asOfDate": "2021-04-18T00:00:00.000",
            "indexLabel": "Index:",
            "indexName": "Morningstar US Market TR USD",
            "enterpriseValueCurrency": "USD"
        }
    },
    "Expanded": {
        "rows": [
            {
                "label": "Price/Forward Earnings",
                "salDataId": "price.forward.earnings.label",
                "isQuantitative": false,
                "datum": [
                    "-14.9031",
                    "-49.7512",
                    "133.3333",
                    "65.3595",
                    "156.25",
                    "384.6154",
                    "-70.922",
                    "61.3497",
                    "95.2381",
                    "175.4386",
                    "175.4386",
                    "178.2437",
                    null
                ],
                "subLevel": ""
            },
            ...
        ],
        "columnDefs": [
            "Calendar",
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "Current",
            "5-Yr",
            "Index"
        ],
        "columnDefs_labels": [
            "tabular.data.label.column.year",
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "valuation.headers.current",
            "valuation.headers.fiveyear",
            "valuation.headers.index"
        ]
    }
}
```

This endpoint is used to mapped to valuation  tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-valuation`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-dividends

curl "https://morning-star.p.rapidapi.com/stock/v2/get-dividends?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "rows": [
        {
            "label": "Dividend Per Share",
            "salDataId": "dividends.per.share.label",
            "datum": []
        },
        {
            "label": "Trailing Dividend Yield %",
            "salDataId": "trailing.dividends.yield.label",
            "datum": [],
            "percentage": true
        },
        {
            "label": "Buyback Yield %",
            "salDataId": "buyback.yield.label",
            "datum": [
                null,
                null,
                null,
                "0.00",
                null,
                null,
                null,
                "0.00",
                null,
                null,
                null,
                null,
                null
            ],
            "percentage": true
        },
        ...
    ],
    "columnDefs_labels": [
        "tabular.data.label.column.year",
        "2011",
        "2012",
        "2013",
        "2014",
        "2015",
        "2016",
        "2017",
        "2018",
        "2019",
        "2020",
        "dividends.headers.current",
        "dividends.headers.oneyearttm",
        "dividends.headers.fiveyear"
    ],
    "dividendData": {
        "label": [
            "exdividend.date.label",
            "declaration.date.label",
            "record.date.label",
            "payable.date.label",
            "dividend.type.label",
            "dividend.amount.label"
        ],
        "upcomingData": [],
        "dividendHistory": []
    },
    "quoteData": [
        {
            "name": "dividendYield",
            "label": "Dividend Yield",
            "salDataId": "dividend.yield.label",
            "date": null,
            "value": null
        },
        ...
    ],
    "footer": {
        "asOfLabel": "As of",
        "distributionCurrency": null
    }
}
```

This endpoint is used to mapped to dividends tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-dividends`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-short-interest

curl "https://morning-star.p.rapidapi.com/stock/v2/get-short-interest?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "sharesOutstanding": 959.8535,
    "floatShares": 771.7854,
    "sharesShorted": 4.6269602E7,
    "sharesShortedDate": "2021-03-31T05:00:00.000",
    "floatSharesShorted": 5.9951,
    "daysToConver": 1.1289,
    "sharesShortedChanged": 3.4355,
    "previousSharesShortedDate": "2021-03-15T05:00:00.000"
}
```

This endpoint is used to mapped to short interest section in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-short-interest`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-operating-performance

curl "https://morning-star.p.rapidapi.com/stock/v2/get-operating-performance?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "_meta": {
        "responseStatus": "200700",
        "hint": "Securities successfully returned",
        "performanceId": "0P0000OQN8"
    },
    "reported": {
        "reportType": "Fiscal",
        "reportType_label": "operating.performance.report.type",
        "columnDefs": [
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "TTM",
            "5-Yr",
            "Index"
        ],
        "columnDefs_labels": [
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "operating.performance.headers.oneyearttm",
            "operating.performance.headers.fiveyear",
            "operating.performance.headers.index"
        ],
        "Collapsed": {
            "rows": [
                {
                    "label": "Return on Assets %",
                    "salDataId": "return.on.assets.reported.label",
                    "datum": [
                        "-46.28",
                        "-43.36",
                        "-4.19",
                        "-7.11",
                        "-12.75",
                        "-4.39",
                        "-7.64",
                        "-3.34",
                        "-2.69",
                        "1.60",
                        "1.60",
                        "-4.87",
                        "7.23653"
                    ],
                    "percentage": true
                },
                ...
            ]
        },
        "Expanded": {
            "rows": [
                {
                    "label": "Financial Leverage",
                    "salDataId": "financial.leverage.reported.label",
                    "datum": [
                        "3.184396",
                        "8.934964",
                        "3.622931",
                        "6.415692",
                        "7.431475",
                        "4.768462",
                        "6.762741",
                        "6.040655",
                        "5.184195",
                        "2.346367",
                        null,
                        null,
                        null
                    ]
                },
                ...
            ]
        }
    },
    "restated": {
        "reportType": "Fiscal",
        "reportType_label": "operating.performance.report.type",
        "columnDefs": [
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "TTM",
            "5-Yr",
            "Index"
        ],
        "columnDefs_labels": [
            "2011",
            "2012",
            "2013",
            "2014",
            "2015",
            "2016",
            "2017",
            "2018",
            "2019",
            "2020",
            "operating.performance.headers.oneyearttm",
            "operating.performance.headers.fiveyear",
            "operating.performance.headers.index"
        ],
        "Collapsed": {
            "rows": [
                {
                    "label": "Return on Assets %",
                    "salDataId": "return.on.assets.restated.label",
                    "datum": [
                        "-46.28",
                        "-43.36",
                        "-4.19",
                        "-7.13",
                        "-12.79",
                        "-4.39",
                        "-7.65",
                        "-3.34",
                        "-2.72",
                        "1.60",
                        "1.60",
                        "-4.87",
                        "7.23653"
                    ],
                    "percentage": true
                },
                ...
            ]
        },
        "Expanded": {
            "rows": [
                {
                    "label": "Financial Leverage",
                    "salDataId": "financial.leverage.restated.label",
                    "datum": [
                        "3.184396",
                        "8.934964",
                        "3.622931",
                        "6.395309",
                        "7.444781",
                        "4.768462",
                        "6.762741",
                        "6.041032",
                        "5.184195",
                        "2.346367",
                        null,
                        null,
                        null
                    ]
                },
                ...
            ]
        }
    },
    "footer": {
        "indexLabel": "Index:",
        "indexName": "Morningstar US Market TR USD",
        "ebitdaCurrency": "USD"
    }
}
```

This endpoint is used to mapped to operating performance tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-operating-performance`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## stock/v2/get-instruments

curl "https://morning-star.p.rapidapi.com/stock/v2/get-instruments?instrumentIds=126.1.TSLA,213.1.BMW,126.1.F,126.1.GM" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "status": "OK",
        "lastPrice": 739.78,
        "lastClose": 738.85,
        "tradingStatus": "Pre-Open",
        "marketCap": 692812660652.1599121094,
        "currencyCode": "USD",
        "currencySymbol": "$",
        "listedCurrency": "USD",
        "tradedCurrency": null,
        "exchangeID": "XNAS",
        "exchangeName": "NASDAQ",
        "exchangeTimeZone": "EST",
        "type": "Equity",
        "dayChange": 0.93,
        "dayChangePer": 0.1259,
        "message": "126.1.TSLA"
    },
    ...
]
```

This endpoint is used to mapped to competitors section in quote tab

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/v2/get-instruments`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
instrumentIds | string (required) | Value of instrumentId field from .../stock/v2/get-competitors endpoint


## stock/get-histories

curl "https://morning-star.p.rapidapi.com/stock/get-histories?PerformanceId=0P00001GJH" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "RequestKey": "0P00001GJH",
        "1D": [],
        "3M": [
            {
                "Volume": 0,
                "Price": 9741.7,
                "DateTime": "2021-01-19T00:00:00Z",
                "Growth": 0.0000,
                "CalcString": "9741.7-9741.7/9741.7",
                "ReferenceDate": "2021-01-19T00:00:00Z"
            },
            ...
        ],
        "1Y": [
            {
                "Volume": 0,
                "Price": 7071.52,
                "DateTime": "2020-04-17T00:00:00Z",
                "Growth": 0.0000,
                "CalcString": "7071.52-7071.52/7071.52",
                "ReferenceDate": "2020-04-17T00:00:00Z"
            },
            ...
        ],
        "5Y": [
            {
                "Volume": 0,
                "Price": 5246.06,
                "DateTime": "2016-04-19T00:00:00Z",
                "Growth": 0.0000,
                "CalcString": "5246.06-5246.06/5246.06",
                "ReferenceDate": "2016-04-19T00:00:00Z"
            },
            ...
        ],
        "MAX": [
            {
                "Volume": 0,
                "Price": 2626.75,
                "DateTime": "2004-05-03T00:00:00Z",
                "Growth": 0.0000,
                "CalcString": "2626.75-2626.75/2626.75",
                "ReferenceDate": "2004-05-03T00:00:00Z"
            },
            ...
        ]
    }
]
```

This endpoint is used to get stock, market histories

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/get-histories`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
PerformanceId | string (required) | Value of PerformanceId field from /market/auto-complete and /market/get-summary APIs

## stock/get-quote (Deprecated)

curl "https://morning-star.p.rapidapi.com/stock/get-quote (Deprecated)?PerformanceId=0P00001GJH" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
Try calling a request yourself
```

This endpoint is used to get stock quote information

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/get-quote (Deprecated)`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
PerformanceId | string (required) | Value of PerformanceId field from /market/auto-complete and /market/get-summary APIs

## stock/get-detail

curl "https://morning-star.p.rapidapi.com/stock/get-detail?PerformanceId=0P00001GJH" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "Name": "Nasdaq Inc",
        "Currency": "USD",
        "Exchange": "XNAS",
        "Type": "ST",
        "TypeName": "Stock",
        "ExchangeShortName": "NASDAQ",
        "ExchangeTimeZoneOffsetFromUTCInSeconds": -14400,
        "CompanyId": "0C000008J5",
        "PerformanceId": "0P000003RU",
        "ShareClassId": "0P000003RU",
        "FundShareClassId": "0P000003RU",
        "InceptionDate": "2002-07-01",
        "Sector": "Financial Services",
        "Industry": "Financial Data & Stock Exchanges",
        "RequestKey": "0P000003RU",
        "Detail": {
            "StarRating": 2,
            "EquityStyle": 5,
            "IsStarRatingBasedOnExtendedPerformance": false,
            "Yield": 1.2200,
            "ConsiderBuying": "Premium",
            "ConsiderSelling": "Premium",
            "CreditRating": "Premium",
            "RevenueTTM": 5627,
            "PriceFairValue": "Premium",
            "ForwardDividendYield": 1.22,
            "PriceProspectiveEarnings": 25.4453,
            "PriceBook": 4.103112,
            "PriceSales": 4.750845,
            "PriceCashFlow": 21.35224,
            "ReturnOnInvestmentCapital": 9.39,
            "OverUnderValued": "Premium",
            "ReturnOnAssets": {
                "TrailingTwelveMonths": 5.84900,
                "FinancialYear1": 5.85,
                "FinancialYear2": 5.23,
                "FinancialYear3": 2.95,
                "FinancialYear4": 4.94,
                "FinancialYear5": 0.82
            },
            "ReturnOnEquity": {
                "TrailingTwelveMonths": 15.45730,
                "FinancialYear1": 15.46,
                "FinancialYear2": 13.96,
                "FinancialYear3": 8.09,
                "FinancialYear4": 12.89,
                "FinancialYear5": 1.92
            },
            "EarningsPerShare": {
                "TrailingTwelveMonths": 5.59,
                "FinancialYear1": 5.59,
                "FinancialYear2": 4.63,
                "FinancialYear3": 2.73,
                "FinancialYear4": 4.3,
                "FinancialYear5": 0.63
            },
            "OperatingMargin": {
                "TrailingTwelveMonths": 23.37,
                "FinancialYear1": 23.37,
                "FinancialYear2": 25.48,
                "FinancialYear3": 24.53,
                "FinancialYear4": 26.22,
                "FinancialYear5": 25.73
            },
            "NetMargin": {
                "TrailingTwelveMonths": 16.5808,
                "FinancialYear1": 16.58,
                "FinancialYear2": 18.16,
                "FinancialYear3": 10.71,
                "FinancialYear4": 18.47,
                "FinancialYear5": 2.86
            },
            "FreeCashFlowMargin": {
                "TrailingTwelveMonths": 18.91,
                "FinancialYear1": 18.91,
                "FinancialYear2": 19.62,
                "FinancialYear3": 21.44
            },
            "QuarterlyEarningsPerShare": {
                "TrailingTwelveMonths": 5.59,
                "Quarter1": 1.34,
                "Quarter2": 1.58,
                "Quarter3": 1.45,
                "Quarter4": 1.22
            },
            "Valuation": {
                "AnalystCoverageStatus": "COVERED",
                "BestRatingType": "Premium",
                "PriceFairValue": {
                    "StarRating34": "Premium",
                    "StarRating45": "Premium",
                    "StarRating12": "Premium",
                    "StarRating23": "Premium"
                },
                "Take": {
                    "FairValue": "Premium",
                    "TrendQualCurrent": "Premium",
                    "CompanyMediumProfile": "Nasdaq Inc is a provider of trading, clearing, exchange technology, regulatory, securities listing, information and public company services.",
                    "Assessment": "Premium",
                    "FairValueUncertainty": "Premium",
                    "PremiumDiscountCurrent": "Premium",
                    "PremiumDiscountValue": "Premium",
                    "EconomicMoat": "Premium",
                    "StewardshipGrade": "Premium"
                }
            },
            "BestRatingType": "Qual",
            "FairValue": 108,
            "Assessment": "Overvalued"
        },
        "RegionAndTicker": "USA:NDAQ",
        "Instrument": "126.1.NDAQ"
    }
]
```

This endpoint is used to get detail information of stock, market

### HTTP Request

`GET https://morning-star.p.rapidapi.com/stock/get-detail`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
PerformanceId | string (required) | Value of PerformanceId field from /market/auto-complete and /market/get-summary APIs

## news/list

curl "https://morning-star.p.rapidapi.com/news/list?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": "20210419191",
        "sourceId": "marketwatch",
        "sourceName": "MarketWatch",
        "providerName": "Dow Jones",
        "title": "Nikola stock drops after Wedbush's Ives cuts price target nearly in half",
        "publishedDate": "2021-04-19T07:43:00-05:00"
    },
    ...
]
```

This endpoint is used to list latest news

### HTTP Request

`GET https://morning-star.p.rapidapi.com/news/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## news/get-details

curl "https://morning-star.p.rapidapi.com/news/get-details?id=sourceId=" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "id": "2020050815238",
    "sourceId": "dow-jones",
    "sourceName": "Global News Select",
    "providerName": "Dow Jones",
    "title": "Elon Musk's Effort to Reopen U.S. Tesla Factory Stalls",
    "publishedDate": "2020-05-08T19:05:46.483-05:00",
    "body": [
        {
            "type": "p",
            "contentObject": [
                {
                    "type": "text",
                    "content": "  By Tim Higgins ",
                    "gated": false
                }
            ],
            "gated": false
        },
        ...
    ]
}
```

This endpoint is used to get news details

### HTTP Request

`GET https://morning-star.p.rapidapi.com/news/get-details`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | Value of id returned in .../news/list endpoint
sourceId | string (required) | Value of sourceId returned in .../news/list endpoint

## articles/list

curl "https://morning-star.p.rapidapi.com/articles/list?performanceId=0P0000OQN8" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
[
    {
        "Id": 1033521,
        "Title": "What Is Greenwashing (And What You Can Do About It)",
        "Locale": "en-US",
        "Status": "Live",
        "Collection": {
            "name": "The Short Answer",
            "id": 374
        },
        "Content": {
            "evergreen": true,
            "LargeIconPath": null,
            "SmallIconPath": null,
            "ClosedCaptioning": null,
            "HDVideoURL": null,
            "VideoPodcastURL": null,
            "VideoFileURL": null,
            "Deck": "In this article, we’ll show you how to quickly size up ESG risk exposure in your investments. ",
            "VideoDescription": null,
            "RemoveArchive": true,
            "Body": "<xhtml xmlns=\"http://cms.morningstar.com/api/v2\"><p><em>Greenwashing </em>is when companies exaggerate their commitment to mitigating risks from environmental, social, and governance factors. Companies can greenwash by making unsubstantiated claims and also by omitting relevant information.</p>\n<p>Greenwashing affects consumers and investors alike. Companies that make false claims about the sustainability of their products profit from duping consumers who believe they are making an earth-friendly or socially conscious choice. Asset managers who claim to follow a sustainability-led mandate but invest in companies with significant ESG-related risk are doing their fund investors a similar disservice. </p>\n<p>It can be very difficult for investors to distinguish between genuine and effective ESG risk-mitigation efforts and greenwashing. And there’s no question that subpar regulatory disclosure requirements have exacerbated the problem. Acknowledging increased investor demand for ESG information, the Securities and Exchange Commission has launched some <a href=\"https://www.sec.gov/sec-response-climate-and-esg-risks-and-opportunities\" target=\"_blank\">initiatives</a> including a <a href=\"https://www.sec.gov/news/press-release/2021-42\" target=\"_blank\">task force</a> focused on identifying material gaps or misstatements regarding ESG risk at the company level and also among investment advisors running ESG strategies. </p>\n<p>While that’s certainly encouraging, meaningful regulatory change is often slow to happen. Europe is just now seeing the fruits of increased disclosure efforts <a href=\"https://ec.europa.eu/info/publications/sustainable-finance-high-level-expert-group_en\" target=\"_blank\">years in the making</a> with the Sustainable Finance Disclosure Regulation. Although the details and timeline for implementation have yet to be finalized, the SFDR will require funds marketed in the European Union to disclose climate, diversity, and governance data. </p>\n<p>U.S. investors don't have to wait in the dark for better regulatory initiatives to come to fruition, though. Companies already disclose--through mandated regulatory filings and optional (for now) corporate sustainability reports--a wealth of information that sustainability-focused analysts use to evaluate companies' products, supply chains, policies, and impact. </p>\n<p>In this article, we’ll show you how to use Morningstar and Sustainalytics research and data to measure ESG risk exposure in your investments. </p>\n<p><strong>Stocks</strong><br/>\nSustainalytics’ ESG Risk Ratings can help investors measure the degree to which ESG issues are putting a company’s enterprise value at risk. The higher the ESG Risk Rating, the higher the company’s unmanaged ESG risk. (Sustainalytics, a Morningstar company, provides <a href=\"https://www.sustainalytics.com/esg-ratings/\" target=\"_blank\">free access to ESG Risk Ratings on over 4,000 companies</a>.)</p>\n<p>An important characteristic of the ESG Risk Rating is that it is an absolute measure of risk. In other words, the scores and ratings are comparable across different issues, companies, and industries.</p>\n<p>The rating is composed of two main parts: \"Exposure\" measures a company’s vulnerability or susceptibility to ESG risks. To a large degree, the industry a company operates in dictates the ESG risk it faces. For example, an oil and gas company will be highly exposed to environmental risk, while a consumer technology business will be more exposed to social issues, such as data privacy. </p>\n<p>The \"Management\" dimension refers to actions taken by a company to manage a particular ESG issue. This can include a company’s ESG issues and policies. Controversies can negatively impact a company’s management score because they often reveal that management initiatives were insufficient or ineffective.</p>\n<p>The ESG Risk Rating blends the exposure score and the management score together. </p>\n<p>Here's a closer look at Tesla <span class=\"CMS__Security\" title=\"0P0000OQN8\">TSLA</span>:</p>\n<p><a href=\"https://www.sustainalytics.com/esg-rating/tesla-inc/1035322998/\"><img alt=\"\" src=\"https://im.morningstar.com/content/CMSImages/15412.PNG\"/></a><br/>\n<em>  - source: Sustainalytics.com</em></p>\n<p>To be clear, we are not saying Tesla is greenwashing. As an electric vehicle producer, Tesla's exposure to carbon-related regulations is significantly lower than other automakers'. Tesla's operations are also relatively clean and efficient compared with those of industry peers, which typically use more energy and emit more pollution.   </p>\n<p>But the company can't escape all the native risks of the auto manufacturing industry--particularly product safety risks--which show up in the \"S\" and \"G\" parts of the ESG risk equation. And Tesla exposes itself to increased safety risks in areas where it is an innovator, such as its automated driving capabilities and autopilot technology.  </p>\n<p>When scoring how well Tesla is managing its exposure to those ESG risks, Sustainalytics analysts evaluate the quality and integrity of the company's board and management (<span class=\"CMS__Document\" title=\"884272\">and any controversies</span>). They also factor in CEO Elon Musk's <a href=\"https://www.sec.gov/Archives/edgar/data/1318605/000119312518035345/d524719ddef14a.htm\" target=\"_blank\">unothodox compensation plan</a>, shareholders' rights, and any negative events the company has had involving labor practices and product safety.  </p>\n<p><strong>Mutual Funds</strong><br/>\nSome funds take a rigorous, in-depth approach to integrating ESG. Others may be labeled ESG, or sustainable, but do very little to mitigate investors’ exposure to companies with unattractive ESG risk profiles. </p>\n<p>If a fund describes itself as an ESG fund in its prospectus and marketing materials, it is reasonable to expect the portfolio <span class=\"CMS__Document\" title=\"1033389\">to favor companies with leading environmental, social, and governance practices</span>. You would expect--at the very least--that the fund would not expose an investor to <em>more </em>ESG risk than a traditional (non-ESG) fund in the same category. </p>\n<p>The <span class=\"CMS__Document\" title=\"949095\">Morningstar Sustainability Rating</span>  is a quick way to measure ESG risk in a fund portfolio. The rating starts with each company’s Sustainalytics ESG Risk Rating, which measures the degree to which individual companies in the portfolio face financial risks from ESG issues. Those individual scores are asset-weighted and rolled up into an overall, portfolio-level rating. The rating is easy to interpret: 5 globes means the overall portfolio has negligible ESG risk; 1 globe means it is exposed to significant ESG risk.</p>\n<p>Here’s what the Sustainability Rating looks like for Calvert Equity <span class=\"CMS__Security\" title=\"FOUSA00G1X\">CEYIX</span>, a fund that states in its prospectus that it incorporates ESG considerations into its investment process.</p>\n<p><a href=\"https://www.morningstar.com/funds/xnas/ceyix/portfolio\"><img alt=\"\" src=\"https://im.morningstar.com/content/CMSImages/15423.png\"/></a><br/>\n<em>  - source: Morningstar.com</em></p>\n<p><span>Calvert Equity's Sustainability Score reveals that its portfolio exposes investors to less unmanaged ESG risk than nearly every other fund in the large-growth Morningstar Category. </span></p>\n<p>As Tony Thomas explains in the fund's <a href=\"https://www.morningstar.com/funds/xnas/ceyix/quote\" target=\"_blank\">analysis</a>, Calvert’s ESG team employs a topnotch approach to ESG research, using a proprietary system to rate and rank companies based on ESG criteria and assess material ESG risks. This helps ensure the fund remains invested in ESG leaders and avoids laggards: If a holding drops off Calvert’s approved list, the portfolio managers must sell within a reasonable time frame. </p>\n<p>Another metric that fund investors can use to evaluate mutual fund portfolios' ESG risk exposure is the Morningstar Low Carbon Designation.</p>\n<p>Developed with Sustainalytics, this designation evaluates how well companies in the portfolio are managing their exposure to climate risk by limiting <span>low carbon transition risks and how much exposure they have to fossil fuels. </span>It rolls the company risk scores up into a portfolio-level score.</p>\n<p><a href=\"https://www.morningstar.com/funds/xnas/esgkx/portfolio\"><img alt=\"\" src=\"https://im.morningstar.com/content/CMSImages/15425.png\"/></a><br/>\n<em>  - source: Morningstar.com</em></p>\n<p>While more funds appear to be avoiding fossil fuels, <span class=\"CMS__Document\" title=\"1033389\">investors should not assume that all sustainable funds do</span>. It's also possible that a portfolio earns a Low Carbon designation but has above-average exposure to ESG risk in the portfolio otherwise, as is the case with Gabelli ESG <span class=\"CMS__Security\" title=\"FOUSA06IGK\">ESGKX</span> (click the screenshot above to see Gabelli ESG's portfolio). </p>\n<p>You can use our <a href=\"https://www.morningstar.com/esg-screener\" target=\"_blank\">ESG Screener</a> to <span>search Morningstar's database for funds that score well in terms of the Sustainability Rating and/or have a Low Carbon designation. </span>See <a href=\"https://www.morningstar.com/articles/1032486\">\"How to Find the Right ESG Fund\"</a> for more.</p></xhtml>",
            "Transcript": null
        },
        "Authors": [
            {
                "id": "352",
                "isPrimary": true,
                "name": "Karen Wallace",
                "Holdings": "vinix newfx POAGX MORN artkx rysex",
                "Profiles": [
                    {
                        "jobTitle": "",
                        "byLine": "Karen Wallace",
                        "shortBio": "Karen Wallace, CFP® is Morningstar’s director of investor education.",
                        "longBio": "Karen Wallace, CFP® is Morningstar’s director of investor education.",
                        "isPrimaryProfile": false
                    },
                    ...
                ],
                "image": "http://im.mstar.com/Content/CMSImages/78x78/352-kwallac-78x78.jpg"
            }
        ],
        "RelatedDocuments": [
            {
                "id": 1033389,
                "title": "Not All Sustainable Funds Are Equally Sustainable",
                "publishDate": "2021-04-14"
            },
            ...
        ],
        "PublishDateUTC": "1618511400000",
        "UpdateDateUTC": "1618586371000",
        "Securities": [
            {
                "shareClassId": "0P0000OQN8",
                "secId": "0P0000OQN8",
                "name": "Tesla Inc",
                "ticker": "TSLA",
                "country": "USA",
                "exchange": "NAS",
                "currency": "USD",
                "securityType": "E0",
                "category": "Auto Manufacturers",
                "parentId": "0C00004EP4"
            },
            ...
        ],
        "Keywords": [
            {
                "id": 2,
                "name": "MUTUALFUNDS",
                "isPrimary": false
            },
			...
        ],
        "AuthorDisclosure": "",
        "Tags": [
            {
                "id": 1002,
                "name": "Commentary",
                "categoryId": 1
            },
            ...
        ]
    },
    ...
]
```

This endpoint is used to list latest articles

### HTTP Request

`GET https://morning-star.p.rapidapi.com/articles/list`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
performanceId | string (required) | Value of performanceId field from .../auto-complete or /get-summary or .../get-movers endpoints

## articles/get-details

curl "https://morning-star.p.rapidapi.com/articles/get-details?id=" \
  -H "x-rapidapi-key: meowmeowmeow"
  -H "x-rapidapi-host: morning-star.p.rapidapi.com"
```

> The above command returns JSON structured like this:

```json
{
    "id": 981538,
    "title": "Tesla Posts a 1Q Profit for the First Time",
    "deck": "We are increasing our fair value estimate to $731 from $239. If a recession can’t stop Tesla then virtually nothing will, and we expect the company to remain a leader in autonomous technology and range. ",
    "locale": "en-US",
    "publishedDate": "2020-04-30",
    "updatedDate": "2020-04-30",
    "paywalled": false,
    "articleType": "evergreen",
    "authors": [
        {
            "holdings": [
                "AMZN",
                "BP",
                "DIS",
                "EXPR",
                "GOOG",
                "GOOGL",
                "IPI",
                "MELI",
                "MOAT",
                "AAPL",
                "AMAT",
                "ECPN",
                "FB",
                "GLW",
                "JNJ",
                "MSFT",
                "SYK"
            ],
            "id": "766",
            "name": "David Whiston",
            "jobTitle": "Sector Strategist",
            "byLine": "David Whiston, CFA, CPA, CFE",
            "shortBio": "David Whiston, CFA, CPA, CFE, is an industrials strategist for Morningstar.",
            "isPrimary": true
        }
    ],
    "authorDisclosure": [],
    "body": [
        {
            "type": "p",
            "contentObject": [
                {
                    "type": "text",
                    "content": "Tesla ",
                    "gated": false
                },
                ...
            ],
            "gated": false
        },
        ...
    ],
    "collection": {
        "name": "Stock Analyst Update",
        "id": 181
    },
    "relatedArticles": [
        {
            "id": 981526,
            "title": "Facebook’s Strong Q1 Encouraging; COVID-19 Risks Remain",
            "publishDate": "2020-04-30"
        },
        ...
    ],
    "tags": [],
    "securities": [
        {
            "shareClassId": "0P0000OQN8",
            "secId": "0P0000OQN8",
            "name": "Tesla Inc",
            "ticker": "TSLA",
            "country": "USA",
            "exchange": "NAS",
            "currency": "USD",
            "securityType": "E0",
            "category": "Auto Manufacturers",
            "parentId": "0C00004EP4"
        }
    ],
    "keywords": [
        {
            "id": 77,
            "name": "EQUITYRESEARCH",
            "isPrimary": true
        }
    ]
}
```

This endpoint is used to get articles details

### HTTP Request

`GET https://morning-star.p.rapidapi.com/articles/get-details`

### Query Parameters

Parameter | Type | Description
--------- | ------- | ----------------------------------------------------------------------------------------------------------------------------
id | string (required) | Value of id returned in .../articles/list endpoint



