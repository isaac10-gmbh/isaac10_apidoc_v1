## Confirmation after Upgrade/Downgrade


```http
GET /api/v1/customer/customer_number/thank_you/subscription_id/upgrade_downgrade HTTP/1.1
```

```javascript
isaac10.thankYouAfterUpgradeDowngrade(subscription_id);
```

> Response

```json
{
  "plan": {
  },
  "subscription": {
}
}
```


<aside class="success">
Before making the function call, the <a href="#customer-authentication">customer must be authenticated</a>.
</aside>

### Params

Parameter | Description
----------|-------------
**customer_number** (in URL) | The number identifying the customer.  
**subscription_id** | The ID of the subscription.


### Response

Parameter | Description
----------|-------------
**plan** | This data is the same as provided when calling `.getPlan()`.
**subscription** | This Data is the same as provided when calling `.thankYouAfterRegister()`.

As described in [Confirmation after Registration](#confirmation-after-registration) the function [Upgrading/Downgrading a Subscription](#upgrading-downgrading-a-subscription) creates a new data record for a subscription, not yet been confirmed. The created ID of this subscription will be used here, in order to confirm the newly created record.
