
### `/collections/{collection_name}/partitions` (GET)

Gets all partitions in a collection starting from `offset` and ends with `page_size`.

#### Request

| Request Component | Value                                       |
| ----------------- | ------------------------------------------- |
| Name              | `/collections/{collection_name}/partitions` |
| Header            | `accept: application/json`                  |
| Body              | N/A                                         |
| Method            | GET                                         |

##### Query Parameters

| Parameter         | Description                                                   | Required? |
| ----------------- | ------------------------------------------------------------- | --------- |
| `collection_name` | Name of the collection.                                       | Yes       |
| `offset`          | Row offset from which the data page starts. The default is 0. | No        |
| `page_size`       | Size of the data page. The default is 10.                     | No        |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/collections/test_collection/partitions?offset=0&page_size=3" -H "accept: application/json"
```

##### Response

```json
{
  "partitions": [
    { "partition_tag": "_default" },
    { "partition_tag": "test_tag" },
    { "partition_tag": "test_2" }
  ],
  "count": 10
}
```