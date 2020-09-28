
### `/collections/{collection_name}` (OPTIONS)

Use this API for Cross-Origin Resource Sharing (CORS).

#### Request

| Request Component | Value                            |
| ----------------- | -------------------------------- |
| Name              | `/collections/{collection_name}` |
| Header            | N/A                              |
| Body              | N/A                              |
| Method            | OPTIONS                          |

#### Query Parameters

| Parameter         | Description             | Required? |
| ----------------- | ----------------------- | --------- |
| `collection_name` | Name of the collection. | Yes       |

#### Example

##### Request

```shell
$ curl -X OPTIONS "http://127.0.0.1:19121/collections/test_collection"
```
