---
id: marketdata
title: Market Data Proto
sidebar_label: marketdata.proto
---

This is the `marketdata.proto` definition used for market data streaming.
[marketdata.proto](/marketdata.proto)


```proto title="marketdata.proto"
syntax = "proto3";

message MarketData {
  string symbol = 1;
  double lastPrice = 2;
  int64 timestamp = 3;
}

