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

Welcome to the API Dojo documentation! You can use our APIs to access official live and structural data from lots of brands which are from various categories.

We currently provide our services via <a href='https://rapidapi.com' target='_blank'>RapidAPI</a> only. You need to register an account on the market platform as developer or consumer to start using our APIs. Please have a look at <a href='https://docs.rapidapi.com/docs/basics-creating-a-project'  target='_blank'>Creating a project</a> to get started.

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
interval | string (required) | One of the followings : d1&#124;d3&#124;ytd&#124;m1&#124;m3&#124;m6&#124;y1&#124;y5

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
interval | string (required) | One of the followings : d1&#124;d3&#124;ytd&#124;m1&#124;m3&#124;m6&#124;y1&#124;y5

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
template | string | One of the following COMMODITY&#124;CURRENCY&#124;INDEX&#124;INDEXFUTURE&#124;RATE&#124;STOCK

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
id | string (required) | One of the following is allowed markets&#124;technology&#124;view&#124;pursuits&#124;politics&#124;green&#124;citylab&#124;businessweek&#124;fixed-income&#124;hyperdrive&#124;cryptocurrencies&#124;wealth&#124;latest&#124;personalFinance&#124;quickTake&#124;world&#124;industries&#124;stocks&#124;currencies&#124;brexit

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
id | string (required) | One of the followings : home-v3&#124;asia-home-v3&#124;europe-home-v3&#124;middle-east-home-v3&#124;africa-home-v3&#124;canada-home-v3

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
template | string | One of the followings : COMMODITY&#124;CURRENCY&#124;INDEX&#124;INDEXFUTURE&#124;RATE&#124;STOCK

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
sort | int | One of the followings : recent_activity_high&#124;recently_sold_high&#124;for_sale_count_high&#124;recommendations_count_high&#124;agent_rating_high

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
prop_type | string | One of the followings (separated by comma for multiple values): single_family&#124;multi_family&#124;condo&#124;mobile&#124;land&#124;farm&#124;other
sort | string | One of the followings : sold_date&#124;beds_high&#124;price_low&#124;price_high&#124;lot_sqft_high

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
prop_type | string | One of the followings (separated by comma for multiple values): single_family&#124;multi_family&#124;condo&#124;mobile&#124;land&#124;farm&#124;other
prop_sub_type | string | One of the followings (separated by comma for multiple values): condo&#124;cond_op&#124;townhouse&#124;co_op
sort | string | One of the followings : relevance&#124;newest&#124;price_low&#124;price_high&#124;photos&#124;open_house_date&#124;sqft_high&#124;price_reduced_date
allows_cats | boolean | false/true - Whether or not cats are allowed to live in properties
allows_dogs | boolean | false/true - Whether or not dogs are allowed to live in properties
lot_sqft_max | int | Max Lot/Acreage size
lot_sqft_min | int | Min Lot/Acreage size
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
features | string | One of the followings (separated by comma for multiple values): recreation_facilities&#124;swimming_pool&#124;washer_dryer&#124;garage_1_or_more&#124;central_air&#124;fireplace&#124;spa_or_hot_tub&#124;dishwasher&#124;community_doorman&#124;community_elevator&#124;furnished&#124;laundry_room&#124;community_no_fee&#124;community_outdoor_space&#124;pets_allowed

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
prop_type | string | One of the followings (separated by comma for multiple values): single_family&#124;multi_family&#124;condo&#124;mobile&#124;land&#124;farm&#124;other
prop_sub_type | string | One of the followings (separated by comma for multiple values): condo&#124;cond_op&#124;townhouse&#124;co_op
is_matterports | boolean | true/false - 3D tours only
is_foreclosure | boolean | true/false - Foreclosures only
has_open_house | boolean | true/false - Open houses only
is_pending | boolean | true/false - Pending only
is_new_plan | boolean | true/false - Homes not yet built
is_contingent | boolean | true/false - Contingent only
is_new_construction | boolean | true/false - New construction only
features | string | One of the followings (separated by comma for multiple values): garage_2_or_more&#124;view&#124;waterfront&#124;golf_course_view&#124;swimming_pool&#124;cul_de_sac&#124;hardwood_floors&#124;basement&#124;fireplace&#124;energy_efficient&#124;disability_features&#124;dining_room&#124;washer_dryer&#124;family_room&#124;den_or_office&#124;game_room&#124;central_air&#124;central_heat&#124;forced_air&#124;single_story&#124;two_or_more_stories&#124;corner_lot&#124;water_view&#124;golf_course_lot_or_frontage&#124;hill_or_mountain_view&#124;ocean_view&#124;city_view&#124;lake_view&#124;river_view&#124;community_security_features&#124;community_swimming_pool&#124;community_boat_facilities&#124;recreation_facilities&#124;community_clubhouse&#124;community_horse_facilities&#124;community_tennis_court&#124;community_park&#124;community_golf&#124;senior_community&#124;community_spa_or_hot_tub&#124;rv_or_boat_parking&#124;horse_facilities&#124;tennis_court&#124;spa_or_hot_tub&#124;garage_1_or_more&#124;garage_3_or_more&#124;carport
sort | string | One of the followings (separated by comma for multiple values): relevance&#124;newest&#124;price_low&#124;price_high&#124;photos&#124;open_house_date&#124;sqft_high&#124;price_reduced_date

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
prop_status | string (required) | One of the followings : for_sale&#124;for_rent&#124;recently_sold
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
prop_type | string | One of the followings (separated by comma for multiple values): single_family&#124; condo&#124; mobile&#124; multi_family&#124; farm&#124; land
sort | string | One of the followings : sold_date&#124;beds_high&#124;price_low&#124;price_high&#124;lot_sqft_high

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
prop_type | string | One of the followings (separated by comma for multiple values): single_family&#124;condo&#124;mobile&#124;multi_family&#124;farm&#124;land
is_matterports | boolean | true/false - 3D tours only
is_foreclosure | boolean | true/false - Foreclosures only
is_pending | boolean | true/false - Pending only
is_contingent | boolean | true/false - Contingent only
is_new_construction | boolean | true/false - New construction only
features | string | One of the followings (separated by comma for multiple values): basement&#124;den_or_office&#124;dining_room&#124;family_room&#124;game_room&#124;washer_dryer&#124;energy_efficient_home&#124;central_air&#124;central_heat&#124;forced_air&#124;carport&#124;garage_1_or_more&#124;garage_2_or_more&#124;garage_3_or_more&#124;rv_or_boat_parking&#124;disability_features&#124;fireplace&#124;hardwood_floors&#124;horse_facilities&#124;spa_or_hot_tub&#124;swimming_pool&#124;tennis_court&#124;single_story&#124;two_or_more_stories&#124;lease_option&#124;pets_allowed&#124;corner_lot&#124;cul_de_sac&#124;golf_course_lot_or_frontage&#124;waterfront&#124;city_view&#124;golf_course_view&#124;hill_mountain&#124;lake_view&#124;ocean_view&#124;river_view&#124;water_view&#124;view&#124;community_swimming_pool&#124;community_boat_facilities&#124;community_spa_or_hot_tub&#124;community_tennis_court&#124;community_golf&#124;community_clubhouse&#124;community_security_features&#124;senior_community&#124;community_horse_facilities&#124;community_park&#124;recreation_facilities&#124;exercise_area
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
prop_type | string | One of the followings (separated by comma for multiple values): apartment&#124;single_family&#124;mapi_condo_townhome&#124;other
sort | string | One of the followings : completeness&#124;photos&#124;freshest&#124;price_low&#124;price_high&#124;photos&#124;newest
allows_cats | boolean | false/true - Whether or not cats are allowed to live in properties
allows_dogs | boolean | false/true - Whether or not dogs are allowed to live in properties
no_pets_allowed | boolean | true/false - Pets are allowed or not (cannot be used with allows_dogs&#124; allows_cats)
sqft_min | int | Min size of the properties
sqft_max | int | Max size of the properties
mapi_community_features | string | One of the followings (separated by comma for multiple values): community_washer_dryer&#124;community_parking&#124;central_air&#124;community_pool&#124;community_gym
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
sort | string | One of the followings : price_low&#124;price_high&#124;photos&#124;newest&#124;open_house_date

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
prop_status | string (required) | One of the followings : for_sale&#124;for_rent
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
prop_status | string (required) | One of the followings : for_sale&#124;for_rent
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
CultureId | int | 1 - English&#124;2 - French



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
BuildingSizeRange | string | 0-5000:0-5,000 sqft&#124;5001-10000:5,001-10,000 sqft&#124;10001-15000:10,001-15,000 sqft&#124;250001-0:Over 250,000 sqft
BedRange | string | 0-0:Any&#124;1-1:1&#124;1-0:1+&#124;2-2:2&#124;2-0:2+&#124;3-3:3&#124;3-0:3+&#124;4-4:4&#124;4-0:4+&#124;5-5:5&#124;5-0:5+
BathRange | string | 0-0:Any&#124;1-1:1&#124;1-0:1+&#124;2-2:2&#124;2-0:2+&#124;3-3:3&#124;3-0:3+&#124;4-4:4&#124;4-0:4+&#124;5-5:5&#124;5-0:5+
UnitRange | string | 0-0:Any&#124;1-1:1&#124;1-0:1+&#124;2-2:2&#124;2-0:2+&#124;3-3:3&#124;3-0:3+&#124;4-4:4&#124;4-0:4+&#124;5-5:5&#124;5-0:5+&#124;....&#124;9-0:9+
LandSizeRange | string | 0-0:Any&#124;1-0:1+ acres&#124;2-0:2+ acres&#124;5-0:5+ acres&#124;10-0:10+ acres&#124;50-0:50+ acres&#124;100-0:100+ acres&#124;200-0:200+ acres&#124;300-0:300+ acres&#124;400-0:400+ acres&#124;500-0:500+ acres&#124;1000-0:1000+ acres
SortBy | int | 1-Price($)&#124;6-Date&#124;11-Virtual Tour&#124;12-Open Houses&#124;13-More Photos
SortOrder | string | A - ascending &#124; D - descending
NumberOfDays | int | Listed since
Keywords | string | Get suitable values from .../keywords/list endpoint, separated by comma for multiple keywords, Ex : Inlaw suite,Income suite
BuildingTypeId | int | 0-No Preference&#124;1-House&#124;2-Duplex&#124;3-Triplex&#124;5-Residential Commercial Mix&#124;6-Mobile Home&#124;12-Special Purpose&#124;14-Other&#124;16-Row / Townhouse&#124;17-Apartment&#124;19-Fourplex&#124;20-Garden Home&#124;26-Modular&#124;27-Manufactured Home/Mobile&#124;28-Commercial Apartment&#124;29-Manufactured Home
OpenHouseStartDate | string | Format date as MM/dd/yyyy, ex : 03/20/2020
OpenHouseEndDate | string | Format date as MM/dd/yyyy, ex : 03/31/2020
OpenHouse | boolean | false/true - Need to use together with OpenHouseStartDate and OpenHouseEndDate parameters
CultureId | int | 1 - English&#124;2 - French
FarmTypeId | int | 0-No Preference&#124;1-Animal&#124;2-Boarding&#124;3-Cash Crop&#124;4-Feed Lot&#124;5-Nursery&#124;6-Market Gardening&#124;7-Hobby Farm&#124;8-Vineyard&#124;9-Orchard&#124;10-Greenhouse&#124;12-Mixed
PriceMin | int | Filter by min price, applied when TransactionTypeId = 2
PriceMax | int | Filter by max price, applied when TransactionTypeId = 2
TransactionTypeId | int | 2-For sale&#124;3-For lease
ZoningTypeGroupId | int | 1-Agricultural&#124;2-Commercial Mixed&#124;3-Commercial Office&#124;4-Commercial Retail&#124;5-Industrial&#124;6-Industrial-Heavy&#124;7-Industrial-Light&#124;8-Industrial-Medium&#124;9-Institutional&#124;10-Other&#124;11-Recreational&#124;12-Residential-High Density&#124;13-Residential-Low Density&#124;14-Residential - Medium Density
ConstructionStyleId | int | 0-No Preference&#124;1-Attached&#124;3-Detached&#124;5-Semi-detached&#124;7-Stacked&#124;9-Link
PropertySearchTypeId | int | 0-No Preference&#124;1-Residential&#124;2-Recreational&#124;3-Condo/Strata&#124;4-Agriculture&#124;5-Parking&#124;6-Vacant Land&#124;8-Multi Family

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
BuildingSizeRange | string | 0-5000:0-5,000 sqft&#124;5001-10000:5,001-10,000 sqft&#124;10001-15000:10,001-15,000 sqft&#124;250001-0:Over 250,000 sqft
BedRange | string | 0-0:Any&#124;1-1:1&#124;1-0:1+&#124;2-2:2&#124;2-0:2+&#124;3-3:3&#124;3-0:3+&#124;4-4:4&#124;4-0:4+&#124;5-5:5&#124;5-0:5+
BathRange | string | 0-0:Any&#124;1-1:1&#124;1-0:1+&#124;2-2:2&#124;2-0:2+&#124;3-3:3&#124;3-0:3+&#124;4-4:4&#124;4-0:4+&#124;5-5:5&#124;5-0:5+
UnitRange | string | 0-0:Any&#124;1-1:1&#124;1-0:1+&#124;2-2:2&#124;2-0:2+&#124;3-3:3&#124;3-0:3+&#124;4-4:4&#124;4-0:4+&#124;5-5:5&#124;5-0:5+&#124;....&#124;9-0:9+
LandSizeRange | string | 0-0:Any&#124;1-0:1+ acres&#124;2-0:2+ acres&#124;5-0:5+ acres&#124;10-0:10+ acres&#124;50-0:50+ acres&#124;100-0:100+ acres&#124;200-0:200+ acres&#124;300-0:300+ acres&#124;400-0:400+ acres&#124;500-0:500+ acres&#124;1000-0:1000+ acres
ZoningTypeGroupId | int | 1-Agricultural&#124;2-Commercial Mixed&#124;3-Commercial Office&#124;4-Commercial Retail&#124;5-Industrial&#124;6-Industrial-Heavy&#124;7-Industrial-Light&#124;8-Industrial-Medium&#124;9-Institutional&#124;10-Other&#124;11-Recreational&#124;12-Residential-High Density&#124;13-Residential-Low Density&#124;14-Residential - Medium Density
ParkingTypeId | int | 1-Attached garage&#124;2-Integrated garage&#124;3-Detached garage&#124;4-Garage&#124;5-Carport&#124;6-Underground&#124;7-Indoor&#124;8-Open&#124;9-Covered&#124;10-Parking pad&#124;11-Paved Yard&#124;35-Boat House&#124;36-Concrete&#124;37-Heated Garage
RentMin | int | Filter by min price, applied when TransactionTypeId = 3
RentMax | int | Filter by max price, applied when TransactionTypeId = 3
PriceMin | int | Filter by min price, applied when TransactionTypeId = 2
PriceMax | int | Filter by min price, applied when TransactionTypeId = 2
TransactionTypeId | int | 2-For sale&#124;3-For rent
NumberOfDays | int | Listed since
OpenHouseStartDate | string | Format date as MM/dd/yyyy, ex : 03/20/2020
OpenHouseEndDate | string | Format date as MM/dd/yyyy, ex : 03/31/2020
OpenHouse | boolean | false/true - Need to use together with OpenHouseStartDate and OpenHouseEndDate parameters
CultureId | int | 1 - English&#124;2 - French
SortOrder | string | A - ascending &#124; D - descending
SortBy | int | 1-Price($)&#124;6-Date&#124;11-Virtual Tour&#124;12-Open Houses&#124;13-More Photos
BuildingTypeId | int | 0-No Preference&#124;1-House&#124;2-Duplex&#124;3-Triplex&#124;5-Residential Commercial Mix&#124;6-Mobile Home&#124;12-Special Purpose&#124;14-Other&#124;16-Row / Townhouse&#124;17-Apartment&#124;19-Fourplex&#124;20-Garden Home&#124;26-Modular&#124;27-Manufactured Home/Mobile&#124;28-Commercial Apartment&#124;29-Manufactured Home
Keywords | string | Get suitable values from .../keywords/list endpoint, separated by comma for multiple keywords, Ex : Inlaw suite,Income suite
FarmTypeId | int | 0-No Preference&#124;1-Animal&#124;2-Boarding&#124;3-Cash Crop&#124;4-Feed Lot&#124;5-Nursery&#124;6-Market Gardening&#124;7-Hobby Farm&#124;8-Vineyard&#124;9-Orchard&#124;10-Greenhouse&#124;12-Mixed
PropertySearchTypeId | int | 0-No Preference&#124;1-Residential&#124;2-Recreational&#124;3-Condo/Strata&#124;4-Agriculture&#124;5-Parking&#124;6-Vacant Land&#124;8-Multi Family
ConstructionStyleId | int | 0-No Preference&#124;1-Attached&#124;3-Detached&#124;5-Semi-detached&#124;7-Stacked&#124;9-Link

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
CultureId | int | 1 - English&#124;2 - French

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
PreferedMeasurementUnit | int | 1-Metric&#124;2-Imperial
CultureId | int | 1 - English&#124;2 - French

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
CultureId | int | 1 - English&#124;2 - French

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

zff | string | Hotel Style - Check for suitable value of \\\"filters/zff\\\" field (separated by comma to specify multiple values) returned in hotel-filters/list endpoint
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
