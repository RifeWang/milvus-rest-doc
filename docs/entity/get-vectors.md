
### `/collections/{collection_name}/vectors?ids={vector_id_list}` (GET)

Obtain vectors by ID.

#### Request

| Request Component | Value                                    |
| ----------------- | ---------------------------------------- |
| Name              | `/collections/{collection_name}/vectors` |
| Header            | `accept: application/json`               |
| Body              | N/A                                      |
| Method            | GET                                      |

#### Query Parameters

| Parameter         | Description                           | Required? |
| ----------------- | ------------------------------------- | --------- |
| `collection_name` | Name of the collection.               | Yes       |
| `vector_id_list`  | Vector id list, separated by commas.  | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 201         | Created                                                           |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/collections/test_collection/vectors?ids=1578989029645098000,1578989029645098001" \
    -H "accept: application/json" \
    -H "Content-Type: application/json"
```

##### Response

```json
{
  "vectors": [
    {
      "id": "1578989029645098000",
      "vector": [0.1]
    },
    {
      "id": "1578989029645098001",
      "vector": [0.2]
    }
  ]
}
```