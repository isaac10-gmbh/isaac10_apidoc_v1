## Creating an extra bill item

```http
GET /api/v1/bill_items HTTP/1.1
```

```javascript
isaac10.createBillItem(params);
```

> Request body / Params

```json
{
  "bill_item": {
    "customer_number": "100001",                                
    "product_name":    "product_name",                           
    "invoice_text":    "Text, being displayed on the bill",  
    "amount_cents":    "2000", // 2000 = 20,00 €                  
    "quantity":        "1",                                    
    "vat":             "19.0",                                  
    "bill_from":       "2015-03-12",                            
    "bill_to":         "2015-04-11"                            
  }
}
```


> Response

```json
{
  "success": true
}
```


<aside class="success">
Before making the function call, you must <a href= "#merchant-authentication"> authenticate yourself</a>.
</aside>

### Validation

Parameter | Description
----------|-------------
**customer_number** | <ul> <li>required </li> <li>must exist and be linked to one of your customers </li>  </ul>
**product_name** | <ul> <li>required </li> <li>must exist and be linked to one of your products </li>  </ul>
**invoice_text** | <ul> <li>required </li> </ul>
**amount_cents** | <ul> <li>required </li> <li> must be in form of a whole number </li> </ul>
**quantity** | <ul> <li>required </li> <li> must be in form of a whole number and be greater than zero</li> </ul>
**vat** | <ul> <li>required </li> <li> must be in form of a decimal number, containing a point as decimal separator and be greater than zero</li> </ul>
**bill_from** | <ul> <li>required </li> <li> must be in form of a date according to ISO-8601 (YYYY-MM-DD)</li> </ul>
**bill_to** | <ul> <li> must be in form of a date according to ISO-8601 (YYYY-MM-DD)</li> <li>must lie after the `bill_from` date </li> </ul>

<aside class="notice">
<strong> How to create a credit item?</strong><br>
To create a credit item, just put a negative amount for <code>amount-cents </code>.
</aside>