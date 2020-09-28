
### `/collections` (GET)

Gets all collections starting from `offset` and ends with `page_size`.

#### Request

| Request Component | Value                      |
| ----------------- | -------------------------- |
| Name              | `/collections`             |
| Header            | `accept: application/json` |
| Body              | N/A                        |
| Method            | GET                        |

##### Query Parameters

| Parameter   | Description                                                   | Required? |
| ----------- | ------------------------------------------------------------- | --------- |
| `offset`    | Row offset from which the data page starts. The default is 0. | No        |
| `page_size` | Size of the data page. The default is 10.                     | No        |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/collections?offset=0&page_size=1" -H "accept: application/json"
```

##### Response

```json
{
    "collections": [
        {
            "collection_name": "test_collection",
            "count": 0,
            "dimension": 1,
            "index": "IVFFLAT",
            "index_file_size": 10,
            "index_params": "{\"nlist\":16384}",
            "metric_type": "L2"
        }
    ],
    "count": 1
}
```
