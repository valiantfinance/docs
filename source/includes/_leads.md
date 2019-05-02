# Leads

🏅

Our Lead API allows third parties to create and read via the API.

## Create Lead

| Item              | Details                                           |
| ----------------- | ------------------------------------------------- |
| Endpoint          | `/api/v1/leads`                                   |
| Supported methods | `POST`                                            |
| Description       | Submits a Lead with the given details to Valiant. |

### Parameters

> Example request

```javascript
var params = {
  first_name: "Isaac",
  last_name: "Newton",
  phone: "0400000000",
  email: "api@valiant.finance",
  months_trading: "12"
};

xhr = new XMLHttpRequest();

xhr.open("POST", "https://valiant.finance/api/v1/leads");
xhr.setRequestHeader("X-AUTH-ID", "<API_ID>");
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type", "application/vnd.api+json");

xhr.onreadystatechange = function() {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
};

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
  url: "https://valiant.finance/api/v1/leads",
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

```bash
curl -iX POST \
  https://valiant.finance/api/v1/leads \
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

| Attribute                          | Type      | Required | Description                                                                                                                                                                                                    |
| ---------------------------------- | --------- | :------: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`first_name`**                   | `string`  |    ✓     | Must be less than 256 characters.                                                                                                                                                                              |
| **`last_name`**                    | `string`  |    ✓     | Must be less than 256 characters.                                                                                                                                                                              |
| **`phone`**                        | `string`  |    ✓     | Must be an Australian phone number and can begin with all valid local area codes, 1800 or 1300.                                                                                                                |
|                                    |           |          | Must follow the following regex format for Ruby: <code>/\A <br/>\A[\(]?(0&#124;\+?61)\s*([23478])[\)]?\s*(([\s\-]_\d){8})\s_\z&#124;<br/>\A[\(]?(1300&#124;1800)[\)]?\s*(([\s\-]*\d){6})\s\*\z<br/>\z/x</code> |
|                                    |           |          | Must follow the following regex format for Javascript: <code>/^^[\(]?(0&#124;\+?61)\s*([23478])[\)]?\s*(([\s\-]_\d){8})\s_\$&#124;^[\(]?(1300&#124;1800)[\)]?\s*(([\s\-]*\d){6})\s\*\$\$/</code>               |
| **`email`**                        | `string`  |    ✓     | Must conform to a valid email address.                                                                                                                                                                         |
|                                    |           |          | Must follow the following regex format for Ruby: <br/><code>/\A((?:\w[-+.]?)+)@([\w-]+(\.[a-z]+)+)\z/</code>                                                                                                   |
|                                    |           |          | Must follow the following regex format for Javascript: <br/><code>/^((?:\w[-+.]?)+)@([\w-]+(\.[a-z]+)+)\$/</code>                                                                                              |
| **`state`**                        | `string`  |          | Must be an accepted value from the [australian_state](#australian-state) options endpoint.                                                                                                                     |
| **`postal_code`**                  | `integer` |          | Must be an Australian postal code, an integer, and exactly 4 digits.                                                                                                                                           |
|                                    |           |          | Must follow the following regex format for Ruby: <br/><code>/\A\d{4}\z/</code>                                                                                                                                 |
|                                    |           |          | Must follow the following regex format for Javascript: <br/><code>/^\d{4}\$/</code>                                                                                                                            |
| **`credit_status`**                | `string`  |          | The credit status of the applicant. Must be an accepted value from the [credit_status](#credit-status) options endpoint.                                                                                       |
| **`abn`**                          | `string`  |          | Australian Business Number. Must be a string containing exactly 11 integers, and unlimited spaces.                                                                                                             |
|                                    |           |          | Must follow the following regex format for Ruby: <br/><code>/\A(?:\d\s?){11}\z/</code>                                                                                                                         |
|                                    |           |          | Must follow the following regex format for Javascript: <br/><code>/^(?:\d\s?){11}\$/</code>                                                                                                                    |
| **`company`**                      | `string`  |          | The entity name. Must be less than 256 characters long.                                                                                                                                                        |
| **`entity_type`**                  | `string`  |          | The applying entity type. Must be an accepted value from the [entity_type](#entity-type) options endpoint.                                                                                                     |
| **`business_performance`**         | `string`  |          | Must be an accepted value from the [business_performance](#business-performance) options endpoint.                                                                                                             |
| **`months_trading`**               | `integer` |          | The months the Lead's business has been trading. Must be a value greater than 0.                                                                                                                               |
| **`average_monthly_sales_amount`** | `string`  |          | The average monthly sales amount. Must be a value greater than 0.                                                                                                                                              |
| **`industry`**                     | `string`  |          | Must be an accepted value from the [industry](#industry) options endpoint.                                                                                                                                     |
| **`invoice_sales`**                | `boolean` |          | Determines if the business has invoice customers. Must be true or false.                                                                                                                                       |
| **`merchant_sales`**               | `boolean` |          | Determines if the business accepts digital payments through a merchant facility. Must be true or false.                                                                                                        |
| **`franchise`**                    | `boolean` |          | Determines if the business is a franchise. Must be true or false.                                                                                                                                              |
| **`cloud_accounting`**             | `boolean` |          | Determines if the business uses a cloud account provider for managing their financials. Must be true or false.                                                                                                 |
| **`accounting_software`**          | `string`  |          | Must be an accepted value from the [accounting_software](#accounting-software) options endpoint.                                                                                                               |
| **`tax_up_to_date`**               | `boolean` |          | Determines if the businesses reporting obligations are up to date with the Australian Taxation Office. Must be true or false.                                                                                  |
| **`tax_outstanding_amount`**       | `string`  |          | The amount currently outstanding with the Australian Taxation office if applicable. Must be a value greater than 0.                                                                                            |
| **`ato_payment_arrangement`**      | `boolean` |          | Determines if the businesses reporting obligations are up to date with the Australian Taxation Office. Must be true or false.                                                                                  |
| **`previous_default`**             | `boolean` |          | Determines if the businesses has has a previous credit default. Must be true or false.                                                                                                                         |
| **`default_liability_amount`**     | `string`  |          | The amount of the previous credit default if applicable. Must be a value greater than 0.                                                                                                                       |
| **`legal_action`**                 | `boolean` |          | Determines if the business has had legal action taken against it in the past due to a credit default. Must be true or false.                                                                                   |
| **`legal_action_description`**     | `string`  |          | A brief description of the legal action if applicable. Must be less than 256 characters.                                                                                                                       |
| **`director_guarantee_available`** | `boolean` |          | Determines if a business director is able to provide a financial guarantee. Must be true or false.                                                                                                             |
| **`prefers_speed_over_rate`**      | `boolean` |          | Determines if a faster time to funding is preferable over a lower rate. Must be true or false.                                                                                                                 |
| **`prefers_redrawable`**           | `boolean` |          | Determines if a redraw facility it preferable over a one off loan. Must be true or false.                                                                                                                      |
| **`requested_amount`**             | `integer` |          | The amount of the loan being requested. Must be a value greater than 0.                                                                                                                                        |
| **`loan_purpose`**                 | `string`  |          | Must be an accepted value from the [loan_purpose](#loan-purpose) options endpoint.                                                                                                                             |
| **`lead_description`**             | `string`  |          | An opportunity to provide further information about the loan request not covered by previous attributes. Must be less than 256 characters.                                                                     |
| **`equipment_class`**              | `string`  |          | Must be an accepted value from the [equipment_class](#equipment-class) options endpoint.                                                                                                                       |
| **`new_equipment`**                | `boolean` |          | Determines if the equipment being purchased is new. Only applicable for equipment related loan purposes. Must be true or false.                                                                                |
| **`utm_campaign`**                 | `string`  |          | The Urchin tracking module (UTM) campaign value. Must be less than 256 characters.                                                                                                                             |
| **`utm_content`**                  | `string`  |          | The Urchin tracking module (UTM) content value. Must be less than 256 characters.                                                                                                                              |
| **`utm_medium`**                   | `string`  |          | The Urchin tracking module (UTM) medium value. Must be less than 256 characters.                                                                                                                               |
| **`utm_source`**                   | `string`  |          | The Urchin tracking module (UTM) source value. Must be less than 256 characters.                                                                                                                               |
| **`utm_term`**                     | `string`  |          | The Urchin tracking module (UTM) term value. Must be less than 256 characters.                                                                                                                                 |

### Response

> Example successful response

```json
{
    :data => {
                :id => "18a14b74-f85c-46a7-bc64-1b963e1ea844",
              :type => :lead,
        :attributes => {
                                     :abn => "46832613142",
                     :accounting_software => "xero",
                 :ato_payment_arrangement => true,
            :average_monthly_sales_amount => 100000,
                    :business_performance => "bad",
                        :cloud_accounting => true,
                                 :company => "The Wind Waker",
                           :credit_status => "great",
                :default_liability_amount => 0,
            :director_guarantee_available => true,
                                   :email => "1bob@prosacco.co",
                             :entity_type => "IND",
                         :equipment_class => "",
                              :first_name => "Fairies",
                               :franchise => true,
                                :industry => "hospitality",
                          :industry_group => "H440",
                           :invoice_sales => true,
                               :last_name => "Orca",
                        :lead_description => "blah",
                            :legal_action => false,
                :legal_action_description => "n.a.",
                            :loan_purpose => "general",
                        :loan_sub_purpose => "inventory",
                          :merchant_sales => true,
                          :months_trading => 24,
                           :new_equipment => "",
                                   :phone => "0400 214 072",
                             :postal_code => "2010",
                      :prefers_redrawable => true,
                 :prefers_speed_over_rate => true,
                        :previous_default => false,
                        :requested_amount => 50000.0,
                                   :state => "NSW",
                  :tax_outstanding_amount => 0,
                          :tax_up_to_date => true,
                            :utm_campaign => "",
                             :utm_content => "",
                              :utm_medium => "",
                              :utm_source => "",
                                :utm_term => "",
                              :created_at => 2019-05-01 00:07:16 UTC,
                                  :status => "Received",
                              :updated_at => 2019-05-01 00:07:16 UTC
        },
             :links => {
            :self => "https://valiant.finance/api/v1/leads/18a14b74-f85c-46a7-bc64-1b963e1ea844"
        }
    }
}
```

If a request is successful, a [`json:api`](http://jsonapi.org/) compliant `JSON` response will be delivered with all resource related information in a `data` key.

| Data             | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| **`id`**         | A unique identifier in `uuid` format generated for the resource by Valiant. |
| **`type`**       | The name of the resource called on.                                         |
| **`attributes`** | A map with values of resource attributes.                                   |


## Read Lead

| Item              | Details                                           |
| ----------------- | ------------------------------------------------- |
| Endpoint          | `/api/v1/leads/:id`                               |
| Supported methods | `GET`                                             |
| Description       | Request the status of a Lead via Lead ID.         |


### Example request

> Example request

```bash
curl -iX GET \
  https://valiant.finance/api/v1/leads/18a14b74-f85c-46a7-bc64-1b963e1ea844 \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json" \
```


### Response

If a request is successful, a [`json:api`](http://jsonapi.org/) compliant `JSON` response will be delivered with all resource related information in a `data` key.

| Data             | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| **`id`**         | A unique identifier in `uuid` format generated for the resource by Valiant. |
| **`type`**       | The name of the resource called on.                                         |
| **`attributes`** | A map with values of resource attributes.  


> Example successful response

```json
{
    :data => {
                :id => "18a14b74-f85c-46a7-bc64-1b963e1ea844",
              :type => :lead,
        :attributes => {
                                     :abn => "46832613142",
                     :accounting_software => "xero",
                 :ato_payment_arrangement => true,
            :average_monthly_sales_amount => 100000,
                    :business_performance => "bad",
                        :cloud_accounting => true,
                                 :company => "The Wind Waker",
                           :credit_status => "great",
                :default_liability_amount => 0,
            :director_guarantee_available => true,
                                   :email => "1bob@prosacco.co",
                             :entity_type => "IND",
                         :equipment_class => "",
                              :first_name => "Fairies",
                               :franchise => true,
                                :industry => "hospitality",
                          :industry_group => "H440",
                           :invoice_sales => true,
                               :last_name => "Orca",
                        :lead_description => "blah",
                            :legal_action => false,
                :legal_action_description => "n.a.",
                            :loan_purpose => "general",
                        :loan_sub_purpose => "inventory",
                          :merchant_sales => true,
                          :months_trading => 24,
                           :new_equipment => "",
                                   :phone => "0400 214 072",
                             :postal_code => "2010",
                      :prefers_redrawable => true,
                 :prefers_speed_over_rate => true,
                        :previous_default => false,
                        :requested_amount => 50000.0,
                                   :state => "NSW",
                  :tax_outstanding_amount => 0,
                          :tax_up_to_date => true,
                            :utm_campaign => "",
                             :utm_content => "",
                              :utm_medium => "",
                              :utm_source => "",
                                :utm_term => "",
                              :created_at => 2019-05-01 00:07:16 UTC,
                                  :status => "Received",
                              :updated_at => 2019-05-01 00:07:16 UTC
        },
             :links => {
            :self => "https://valiant.finance/api/v1/leads/18a14b74-f85c-46a7-bc64-1b963e1ea844"
        }
    }
}

```
