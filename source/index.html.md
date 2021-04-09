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

RapidAPI uses token key to allow access to all APIs on the platform. You need to generate a token key for a new app in your developer control panel of RapidAPI at <a href='https://rapidapi.com/developer'>https://rapidapi.com/developer</a>. 

You then need to learn how to pass the token key via request HEADER as following :

`x-rapidapi-key: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

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
query | String | Any thing you are familiar with, stock, index, organization, etc...

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
id | String | The value of id field returned in .../market/auto-complete endpoint.

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
id | String | The currency code, separated by comma to query multiple currencies at once

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
id | String | The value of id field returned in .../market/auto-complete endpoint.
interval | String | One of the followings : d1|d3|ytd|m1|m3|m6|y1|y5

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
id | String | The value of id field returned in .../market/auto-complete endpoint, separated by comma to query multiple stickers at once.

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
id | String | The value of id field returned in .../market/auto-complete endpoint, separated by comma to query multiple stickers at once.

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
id | String | The value of id field returned in .../market/auto-complete endpoint
interval | String | One of the followings : d1|d3|ytd|m1|m3|m6|y1|y5

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
id | String | The value of id field returned in .../market/auto-complete endpoint
template | String | One of the following COMMODITY|CURRENCY|INDEX|INDEXFUTURE|RATE|STOCK

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
id | String | The value of id field returned in .../market/auto-complete endpoint

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
id | String | One of the following is allowed markets|technology|view|pursuits|politics|green|citylab|businessweek|fixed-income|hyperdrive|
||cryptocurrencies|wealth|latest|personalFinance|quickTake|world|industries|stocks|currencies|brexit

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
id | String | One of the followings : home-v3|asia-home-v3|europe-home-v3|middle-east-home-v3|africa-home-v3|canada-home-v3

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
id | String | The value of id field returned in .../market/auto-complete endpoint
template | String | One of the followings : COMMODITY|CURRENCY|INDEX|INDEXFUTURE|RATE|STOCK

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
internalID | String | Get suitable value from .../stories/list or .../news/list or .../news/list-by-region endpoints
