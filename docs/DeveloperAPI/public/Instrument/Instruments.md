## Overview

This API returns a list of available instruments such as stocks, indices, and derivatives. It is used to populate instrument dropdowns or symbol lists in trading interfaces.

---

###  Sample Json Data
| Field             | Value                        |
|------------------|------------------------------|
| InstrumentId     | 2042700000155916             |
| InstrumentName   | ZYDUSLIFE26SEP241520PE       |
| ExchangeSegment  | NSEFO                        |
| Exchange         | NSE                          |
| ExpiryDate       | 2024-09-26                   |
| InstrumentType   | Options                      |
| LotSize          | 900                          |
| OptionType       | PE                           |
| PriceBandHigh    | 346.95                       |
| PriceBandLow     | 454.75                       |
| StrikePrice      | 1520                         |
| Symbol           | ZYDUSLIFE                    |
| TickSize         | 0.05                         |

### Json Object sample

This section describes the fields and structure of instrument data returned from the Blitz Gateway API. Instrument types include:

-  Equity  
-  Index  
-  Futures  
-  Options  

---


# Equity

```json
{
  "instrumentId": 1010010000014751,
  "instrumentName": "021NSETEST",
  "exchangeSegment": "NSECM",
  "exchange": "NSE",
  "expiryDate": "01/01/0001",
  "instrumentType": "EQUITY",
  "lotSize": 0,
  "optionType": "",
  "priceBandHigh": 180,
  "priceBandLow": 220,
  "strikePrice": 0.0,
  "symbol": "021NSETEST",
  "tickSize": 0.05
}
```
# Index

```json
{
  "instrumentId": 1010010002000001,
  "instrumentName": "NIFTY 50",
  "exchangeSegment": "NSECM",
  "exchange": "NSE",
  "expiryDate": "01/01/0001",
  "instrumentType": "INDEX",
  "lotSize": 0,
  "optionType": "",
  "priceBandHigh": 0.0,
  "priceBandLow": 0.0,
  "strikePrice": 0.0,
  "symbol": "NIFTY 50",
  "tickSize": 0.0
}
```
# Futures
```json
{
  "instrumentId": 2042700000035002,
  "instrumentName": "ABB26SEP24FUT",
  "exchangeSegment": "NSEFO",
  "exchange": "NSE",
  "expiryDate": "2024-09-26T00:00:00",
  "instrumentType": "Futures",
  "lotSize": 125,
  "optionType": "XX",
  "priceBandHigh": 7902.9,
  "priceBandLow": 9659.1,
  "strikePrice": 0,
  "symbol": "ABB",
  "tickSize": 0.05
}
```
# Options
``` json
{
  "instrumentId": 2042690000035005,
  "instrumentName": "BANKNIFTY25SEP2443300CE",
  "exchangeSegment": "NSEFO",
  "exchange": "NSE",
  "expiryDate": "2024-09-25T00:00:00",
  "instrumentType": "Options",
  "lotSize": 15,
  "optionType": "CE",
  "priceBandHigh": 8719.25,
  "priceBandLow": 12373.35,
  "strikePrice": 43300,
  "symbol": "BANKNIFTY",
  "tickSize": 0.05
}
```
# Field Descriptions for Instrument Data

| Field Name        | Type       | Description                                                                 |
|------------------|------------|-----------------------------------------------------------------------------|
| InstrumentId      | Integer    | Unique identifier assigned to the instrument by the system/vendor.         |
| InstrumentName    | String     | Full trading symbol including expiry, strike price, and option type.       |
| ExchangeSegment   | String     | Trading segment in the exchange (e.g., NSEFO for NSE Futures & Options).   |
| Exchange          | String     | Name of the exchange where the instrument is listed (e.g., NSE, BSE).      |
| ExpiryDate        | DateTime   | The expiry date of the instrument (applicable for derivatives).            |
| InstrumentType    | String     | Type of instrument: `Equity`, `Options`, `Futures`, etc.                   |
| LotSize           | Integer    | Number of units in one lot (used in derivative contracts).                 |
| OptionType        | String     | `CE` for Call Option, `PE` for Put Option (only for options).              |
| PriceBandHigh     | Float      | The upper circuit limit for the instrument's price.                        |
| PriceBandLow      | Float      | The lower circuit limit for the instrument's price.                        |
| StrikePrice       | Float      | The strike price of the option (applicable only for options).             |
| Symbol            | String     | Underlying asset's symbol or base trading symbol.                          |
| TickSize          | Float      | Minimum allowed price movement (used for price precision).                |
