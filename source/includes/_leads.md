# Leads

🏅

Our Lead API allows third parties to directly submit Leads to Valiant via the API.

## Create a Lead

| Item              | Details                                             |
| ----------------- | --------------------------------------------------- |
| Endpoint          | `/api/v1/leads`                                     |
| Supported methods | `POST`                                              |
| Description       | Submits a Lead with the given details to Valiant.   |

### Parameters

> Example request

```javascript
var params = {
  "first_name":     "Isaac",
  "last_name":      "Newton",
  "phone":          "0400000000",
  "email":          "api@valiant.finance",
  "months_trading": "12"
}

xhr = new XMLHttpRequest();

xhr.open("POST", "https://mercury-summer.valiant.finance/api/v1/leads");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send(JSON.stringify(params));
```

```jquery
var params = {
  "first_name":     "Isaac",
  "last_name":      "Newton",
  "phone":          "0400000000",
  "email":          "api@valiant.finance",
  "months_trading": "12"
}

$.ajax({
  url: "https://mercury-summer.valiant.finance/api/v1/leads",
  type: "POST",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },
  data: JSON.stringify(params),

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```shell
curl -iX POST \
  https://mercury-summer.valiant.finance/api/v1/leads \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json" \
  -d '{
        "first_name":     "Isaac",
        "last_name":      "Newton",
        "email":          "api@valiant.finance",
        "phone":          "0400000000",
        "months_trading": "12"
      }'
```

Below lists a detail of accepted parameters that can be posted to the endpoint as a part of a valid `JSON` payload. A number of attributes are required.

| Attribute                           | Type      | Required | Description                           |
| ----------------------------------  | --------- | :------: | ------------------------------------- |
| **`first_name`**                    | `string`  | ✓        | Must be less than 256 characters. |
| **`last_name`**                     | `string`  | ✓        | Must be less than 256 characters. |
| **`phone`**                         | `string`  | ✓        | Must be an Australian phone number and can begin with all valid local area codes, 1800 or 1300. |
| **`email`**                         | `string`  | ✓        | Must conform to a valid email address. |
| **`state`**                         | `string`  |          | Must be an accepted value from the [australian_state](#australian-state) options endpoint. |  
| **`postal_code`**                   | `integer` |          | Must be an Australian postal code, an integer, and exactly 4 digits. |
| **`credit_status`**                 | `string`  |          | The credit status of the applicant. Must be an accepted value from the [credit_status](#credit-status) options endpoint. |
| **`abn`**                           | `string`  |          | Australian Business Number. Must be a string containing exactly 11 integers, and unlimited spaces.   |
| **`company`**                       | `string`  |          | The company name. Must be less than 256 characters long.      |
| **`business_performance`**          | `string`  |          | Must be an accepted value from the [business_performance](#business-performance) options endpoint.      |
| **`months_trading`**                | `integer` |          | The months the Lead's business has been trading. Must be a value greater than 0. |
| **`average_monthly_sales_amount`**  | `string`  |          | The average monthly sales amount. Must be a value greater than 0. |
| **`invoice_sales`**                 | `boolean` |          | Determines if the business has invoice customers. Must be true or false. |
| **`merchant_sales`**                | `boolean` |          | Determines if the business accepts digital payments through a merchant facility. Must be true or false. |
| **`franchise`**                     | `boolean` |          | Determines if the business is a franchise. Must be true or false. |
| **`cloud_accounting`**              | `boolean` |          | Determines if the business uses a cloud account provider for managing their financials. Must be true or false. |
| **`tax_up_to_date`**                | `boolean` |          | Determines if the businesses reporting obligations are up to date with the Australian Taxation Office. Must be true or false. |
| **`tax_outstanding_amount`**        | `string`  |          | The amount currently outstanding with the Australian Taxation office if applicable. Must be a value greater than 0. |
| **`ato_payment_arrangement`**       | `boolean` |          | Determines if the businesses reporting obligations are up to date with the Australian Taxation Office. Must be true or false. |
| **`previous_default`**              | `boolean` |          | Determines if the businesses has has a previous credit default. Must be true or false. |
| **`default_liability_amount`**      | `string`  |          | The amount of the previous credit default if applicable. Must be a value greater than 0. |
| **`legal_action`**                  | `boolean` |          | Determines if the business has had legal action taken against it in the past due to a credit default. Must be true or false. |
| **`legal_action_description`**      | `string`  |          | A brief description of the legal action if applicable. Must be less than 256 characters. |
| **`director_guarantee_available`**  | `boolean` |          | Determines if a business director is able to provide a financial guarantee. Must be true or false. |
| **`prefers_speed_over_rate`**       | `boolean` |          | Determines if a faster time to funding is preferable over a lower rate. Must be true or false. |
| **`prefers_redrawable`**            | `boolean` |          | Determines if a redraw facility it preferable over a one off loan. Must be true or false. |
| **`requested_amount`**              | `integer` |          | The amount of the loan being requested. Must be a value greater than 0. |
| **`loan_purpose`**                  | `string`  |          | Must be an accepted value from the [loan_purpose](#loan-purpose) options endpoint.    |
| **`lead_description`**              | `string`  |          | An opportunity to provide further information about the loan request not covered by previous attributes. Must be less than 256 characters.   |

### Response

> Example successful response

```json
{
  "data": {
    "id": "6bbba93f-48c4-413b-88cf-de6436ccb20c",
    "type": "leads",
    "attributes": {
      "created_at": "2017-08-17T00:00:00.001Z"
    }
  }
}
```

If a request is successful, a [`json:api`](http://jsonapi.org/) compliant `JSON` response will be delivered with all resource related information in a `data` key.

| Data             | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| **`id`**         | A unique identifier in `uuid` format generated for the resource by Valiant. |
| **`type`**       | Pluralized name of the resource called on.                                  |
| **`attributes`** | A map with values of resource attributes.                                   |

### Attributes

The values of attributes included in the `attributes` hash are:

| Attribute        | Description                                 |
| ---------------- | ------------------------------------------- |
| **`created_at`** | The UTC datetime the resource was created.  |

<aside class="notice">
  Future releases of the Valiant API will allow the lookup of Leads using the returned <code>id</code> here as a reference. Be sure to store the returned <code>id</code> if you think you might want to look up the Lead at a later date.
</aside>
