
### `/system/{msg}` (GET)

Gets information about the Milvus server.

#### Request

| Request Component | Value                      |
| ----------------- | -------------------------- |
| Name              | `/system/{msg}`            |
| Header            | `accept: application/json` |
| Body              | N/A                        |
| Method            | GET                        |

##### Query Parameters

| Parameter | Description                                                       | Required? |
| --------- | ----------------------------------------------------------------- | --------- |
| `msg`     | Type of the message to return. You can use `status` or `version`. | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/system/version" -H "accept: application/json"
```

##### Response

```json
{"code":0,"message":"OK","reply": "0.8.0" }
```