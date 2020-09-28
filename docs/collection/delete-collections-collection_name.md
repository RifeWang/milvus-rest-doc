
### `/collections/{collection_name}` (DELETE)

Drops a collection by name.

#### Request

| Request Component | Value                            |
| ----------------- | -------------------------------- |
| Name              | `/collections/{collection_name}` |
| Header            | `accept: application/json`       |
| Body              | N/A                              |
| Method            | DELETE                           |

##### Query Parameters

| Parameter         | Description             | Required? |
| ----------------- | ----------------------- | --------- |
| `collection_name` | Name of the collection. | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 204         | Deleted                                                           |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X DELETE "http://127.0.0.1:19121/collections/test_collection" -H "accept: application/json"
```

If the deletion is successful, no message will be returned.
