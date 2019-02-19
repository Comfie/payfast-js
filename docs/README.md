# PayFast JS
---
Open-source library used/built by logistics startup [GetTruck](https://gettruck.co.za) for working with the PayFast REST API

Working with the PayFast REST API is a nightmare. We had to do a whole bunch of URL concatenation, which is not a great approach. That's why we decided to build a neat library around the API for a more cleaner experience 

**NB! Still needs a lot of work done, don't use in production just yet 😬**

## Usage
#### Config

```javascript
const { PayFastAPI } = require("payfast-js");

const payfast = new PayFastAPI({ merchant_id: "<id>", merchant_key: "<key>" });
```

#### Add payment details

```javascript
payfast.addPaymentDetails({
  amount: "4000",
  item_name: "Samsung 55' TV"
});
```

#### Add reference details

```javascript 
payfast.addReferenceDetails({
  m_payment_id: "12345678",
  custom_str1: "asdfgh",
  custom_str2: "qwerty"
});
```

#### Add return, cancel and notify URLs

```javascript
payfast.returnURL("<success-page-url>");
payfast.cancelURL("<cancel-page-url>");
payfast.notifyURL("<notify-url>");
```

#### Generate URL

```javascript
payfast.generateURL() // returns payfast URL for payment processing
```