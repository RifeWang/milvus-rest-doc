### `/state` (GET)

Checks whether the web server is running.

#### Request

| Request Component | Value                      |
| ----------------- | -------------------------- |
| Name              | `/state`                   |
| Header            | `accept: application/json` |
| Body              | N/A                        |
| Method            | GET                        |

#### Response

| Status code | Description                |
| ----------- | -------------------------- |
| 200         | The request is successful. |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/state" -H "accept: application/json"
```

##### Response

```json
{ "message": "Success", "code": 0 }
```
