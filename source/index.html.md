---
title: Dripit Integration

language_tabs:
  - javascript

toc_footers:
  - <a href='http://dripit.io'>Sign Up</a>

search: true
---
# Loading dripit.js

> Add the following script into your website template's `<head>` section

```javascript
<script>
(function (a, b, c, d, e, f) {
  a[c] = a[c] || function () {
      (a[c].q = a[c].q || []).push(arguments)
    }, a.DripitGlobalObject = a[c], a[c].t = 1 * new Date, a[c].k = e, a[c].e = f;
  var g = b.createElement("script");
  g.async = 1, g.src = d;
  var h = b.getElementsByTagName("script")[0];
  h.parentNode.insertBefore(g, h)
}(window, document, "Dripit", "https://d16ibetoxqxf3g.cloudfront.net/dripit.js.gz", {{SHOP_TOKEN}}, "//d1lp7mkioca5jv.cloudfront.net/1.gif"));
<script>
```

> Make sure to set `SHOP_TOKEN`!

Your `SHOP_TOKEN` can be found at Dripit [integration page](http://attribution.dripit.io/auth/integration) in your profile.

# Sending Events

## Cart Events

```javascript
// for example
window.Tracker('cart', {
  customer_id: "user1"
});
```


### Available parameters

| Parameter     | Required?     | Example value  | Description |
| ------------- |:-------------:|:--------------:| ----------- |
| `customer_id` | Yes           | "user1"        | Unique customer identifier (more info below). Set to `null` if `undefined` |


## Checkout Events

```javascript
// for example
window.Tracker('checkout', {
  customer_id: "user1"
});
```


### Available parameters

| Parameter     | Required?     | Example value  | Description |
| ------------- |:-------------:|:--------------:| ----------- |
| `customer_id` | Yes           | "user1"        | Unique customer identifier (more info below). Set to `null` if `undefined` |

## Order Events

```javascript
// for example
window.Tracker('order', {
  customer_id: "user1",
  order_id: "order1",
  total_price: 204.99,
  currency: "EUR",
  item_count: 2,
  items: [
  {
    id: 58201,
    price: 104.99,
    title: "Kindle Paperwhite"
  },
  {
    id: 93201,
    price: 100.00,
    title: "Moto G 1st gen"
  }
  ]
});
```


### Available parameters

| Parameter     | Required?     | Example value  | Description |
| ------------- |:-------------:|:--------------:| ----------- |
| `customer_id` | Yes           | "user1"        | Unique customer identifier (more info below). Set to `null` if `undefined` |
| `order_id`    | Yes           | "order1"       | Unique order identifier (more info below). |
| `total_price` | Yes           | 204.99         | Total price of items in cart |
| `item_count`  | Yes           | 2              | Count of items in cart |
| `currency  `  | Yes           | "EUR"          | Cart currency([ISO_4217](https://en.wikipedia.org/wiki/ISO_4217#Currency_numbers)) |
| `items`       | Yes           | Array(items)   | Array of items |
| `items.id`    | Yes           | 53425          | Unique item id. Optionaly set to `null`. |
| `items.price` | Yes           | 123.99         | Items price    |
| `items.title` | Yes           | "title"        | Items name     |

