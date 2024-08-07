---
sidebar_position: 7
sidebar_label: open_short (FUTURES)
hide_title: false
---

import { Highlight } from "../../../../../src/components/Highlight.js";

# open_short (FUTURES)

<Highlight color="#ffba00"> This function can only be used in trade(). </Highlight>

To put one open_short order. Each period can put at max 500# orders.

## Input

```typescript
exchange: string;
pair: string;
amount: number;
type: OrderType;
price: number;
```

> Check [OrderType](/docs/developer/api/python/ca-objects/order-type)

## Example

To put one open_short order with market price for 1 amount. It is not necassery to set price with market price order.

```python
exchange, pair, base, quote = CA.get_exchange_pair()
CA.open_short(exchange, pair, 1, CA.OrderType.MARKET)
```

To put one open_short order with limit price for 1 amount. The limit price is set as close_price.

```python
exchange, pair, base, quote = CA.get_exchange_pair()
close_price = candles[exchange][pair][0]['close']
CA.open_short(exchange, pair, 1, CA.OrderType.LIMIT, close_price)
```
