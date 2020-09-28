
### `/collections/{collection_name}/vectors` (POST)

Inserts entities to a collection.

> Note: It is recommended that you do not insert more than 1 million entities per request.

#### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/collections/{collection_name}/vectors</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
    "partition_tag": "part",
    "vectors": [[0.1],[0.2],[0.3],[0.4]]
}
</code></pre> </td></tr>
<tr><td>Method</td><td>POST</td></tr>
</table>

##### Body Parameters

| Parameter       | Description                                                                                                                                                                                                                      | Required? |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| `partition_tag` | Tag of the partition to insert vectors to.                                                                                                                                                                                       | No        |
| `vectors`      | vectors to insert to the collection.                                                                                                                                                                                             | Yes       |
| `ids`           | IDs of the entities to insert to the collection. If you assign IDs to the entities, you must provide IDs for all vectors in the collection. If you do not specify this parameter, Milvus automatically assigns IDs to the vectors. | No        |

> Note: Type of items of `entities` depends on the metric used by the collection. If the collection uses `L2` or `IP`, you must use `float`. If the collection uses `HAMMING`, `JACCARD`, or `TANIMOTO`, you must use `uint8`.

##### Query Parameters

| Parameter         | Description             | Required? |
| ----------------- | ----------------------- | --------- |
| `collection_name` | Name of the collection. | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 201         | Created                                                           |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X POST "http://127.0.0.1:19121/collections/test_collection/vectors" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "vectors": [[0.1],[0.2],[0.3],[0.4]]
  }'
```

##### Response

```json
{
  "ids": [
    "1578989029645098000",
    "1578989029645098001",
    "1578989029645098002",
    "1578989029645098003"
  ]
}
```