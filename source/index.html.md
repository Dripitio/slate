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
(function (r, e, a, c, h, _, l, y) {
  r[a] = r[a] || function () {
    (r[a].q = r[a].q || []).push(arguments);
  };
  // Save current timestamp.
  r[a].t = 1 * new Date();
  // Save access key.
  r[a].k = h;
  // Save endpoint
  r[a].e = _;

  // Create new async script tag.
  l = e.createElement('script');
  l.async = 1;
  l.src = c;

  // Insert it before first script tag in the page.
  y = e.getElementsByTagName('script')[0];
  y.parentNode.insertBefore(l, y);
}(window, document, 'Tracker', 'https://d16ibetoxqxf3g.cloudfront.net/dripit.js.gz', '<TOKEN>', '<ENDPOINT>'));
<script>
```

> Make sure to replace <TOKEN> and <ENDPOINT> with your specific configuration.

Both TOKEN and ENDPOINT currently are received after you have successfully completed registration. After completing this step correctly Dripit will start to track users pageview events.

# Sending Events

## Cart Events

```javascript
// for example
window.Tracker('cart', {
  token: "user1",
  total_price: 204.99,
  currency: 'EUR',
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
| `total_price` | Yes           | 204.99         | Total price of items in cart |
| `item_count`  | Yes           | 2              | Count of items in cart |
| `currency  `  | Yes           | 'EUR'          | Cart currency([ISO_4217 (https://en.wikipedia.org/wiki/ISO_4217#Currency_numbers)) |
| `items`       | Yes           | Array(items)   | Array of items |
| `items.id`    | Yes           | 53425          | Unique item id |
| `items.price` | Yes           | 123.99         | Items price    |
| `items.title` | Yes           | 'title'        | Items name     |


## Checkout Events

```javascript
// for example
window.Tracker('checkout', {
  token: "user1",
  total_price: 204.99,
  currency: 'EUR',
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
| `total_price` | Yes           | 204.99         | Total price of items in cart |
| `item_count`  | Yes           | 2              | Count of items in cart |
| `currency  `  | Yes           | 'EUR'          | Cart currency([ISO_4217 (https://en.wikipedia.org/wiki/ISO_4217#Currency_numbers)) |
| `items`       | Yes           | Array(items)   | Array of items |
| `items.id`    | Yes           | 53425          | Unique item id |
| `items.price` | Yes           | 123.99         | Items price    |
| `items.title` | Yes           | 'title'        | Items name     |

## Order Events

```javascript
// for example
window.Tracker('order', {
  token: "user1",
  total_price: 204.99,
  currency: 'EUR',
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
| `total_price` | Yes           | 204.99         | Total price of items in cart |
| `item_count`  | Yes           | 2              | Count of items in cart |
| `currency  `  | Yes           | 'EUR'          | Cart currency([ISO_4217 (https://en.wikipedia.org/wiki/ISO_4217#Currency_numbers)) |
| `items`       | Yes           | Array(items)   | Array of items |
| `items.id`    | Yes           | 53425          | Unique item id |
| `items.price` | Yes           | 123.99         | Items price    |
| `items.title` | Yes           | 'title'        | Items name     |

