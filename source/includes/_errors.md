# Errors

⚠️

The Valiant API uses conventional `HTTP` response codes to indicate the the [`HTTP` status](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) an API request.

* HTTP status codes in the `2xx` range indicate **success 🎉**
* HTTP status codes in the `4xx` range indicate an **error** given the request 🚫
    * e.g., the request was unauthorized, a required parameter was omitted, a validation failed, etc.
* HTTP status codes in the `5xx` range indicate an **internal server error** on the Valiant side 💥

### HTTP status code summary

| Code                 | Meaning                                                                  |
| -------------------- | ------------------------------------------------------------------------ |
| `200 OK`             | Everything worked as expected.                                           |
| `201 Created`        | The resource was created successfully.                                   |
| `400 Bad Request`    | The request was unacceptable, often due to missing a required parameter. |
| `401 Unauthorized`   | No valid authentication headers found.                                   |
| `402 Request Failed` | The parameters were valid but the request failed.                        |
| `404 Not Found`      | The requested resource doesn't exist.                                    |
| `500 Server Error`   | Something went wrong on Valiant's end.                                   |
