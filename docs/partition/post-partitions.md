
### `/collections/{collection_name}/partitions` (POST)

Creates a partition in a collection.

#### Request

| Request Component | Value                                       |
| ----------------- | ------------------------------------------- |
| Name              | `/collections/{collection_name}/partitions` |
| Header            | `accept: application/json`                  |
| Body              | `{ "partition_tag": "test_tag" }`           |
| Method            | POST                                        |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 201         | Created                                                           |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X POST "http://127.0.0.1:19121/collections/test_collection/partitions" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{"partition_tag": "test"}'
```

##### Response

```json
{ "message": "OK", "code": 0 }
```
