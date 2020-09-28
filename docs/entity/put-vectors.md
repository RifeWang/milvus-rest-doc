
### `/collections/{collection_name}/vectors` (PUT)

## 1. Searches vectors in a collection.

#### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/collections/{collection_name}/vectors</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "search": {
      "topk": integer($int64),
      "partition_tags": [string],
      "file_ids": [string],
      "vectors": [[number($float/$uint8)]]
      "params": {
          "nprobe": 16
      }
  }
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>
</table>

##### Body Parameters

| Parameter  | Description                                                                                                                                                                                  | Required? |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| `topk`     | The top k most similar results of each query vector.                                                                                                                                         | Yes       |
| `tags`     | Tags of partitions that you need to search. You do not have to specify this value if the collection is not partitioned or you wish to search the whole collection.                           | No        |
| `file_ids` | IDs of the vector files. You do not have to specify this value if you do not use Milvus in distributed scenarios. Also, if you assign a value to `file_ids`, the value of `tags` is ignored. | No        |
| `vectors`  | Vectors to query.                                                                                                                                                                            | Yes       |
| `params`   | Extra params for search. Please refer to [Index and search parameters](#Index-and-search-parameters) to get more detail information.                                                                                        | Yes       |

> Note: Type of items of vectors depends on the metric used by the collection. If the collection uses `L2` or `IP`, you must use `float`. If the collection uses `HAMMING`, `JACCARD`, or `TANIMOTO`, you must use `uint8`.

##### Query Parameters

| Parameter         | Description             | Required? |
| ----------------- | ----------------------- | --------- |
| `collection_name` | Name of the collection. | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/collections/test_collection/vectors" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "search":{
      "topk":2,
      "vectors":[[0.1]],
      "params":{"nprobe":16}
    }
  }'
```

##### Response

```json
{
  "num": 1,
  "results": [
    [
      { "id": "1578989029645098000", "distance": "0.000000" },
      { "id": "1578989029645098001", "distance": "0.010000" }
    ]
  ]
}
```

## 2. Delete vectors

#### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/collections/{collection_name}/vectors</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "delete": {
     "ids": [$string]
  }
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>
</table>

##### Body Parameters

| Parameter | Description     | Required? |
| --------- | --------------- | --------- |
| ids       | IDs of vectors. | Yes       |

##### Query Parameters

| Parameter         | Description             | Required? |
| ----------------- | ----------------------- | --------- |
| `collection_name` | Name of the collection. | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/collections/test_collection/vectors" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "delete": {
      "ids": ["1578989029645098000"]
    }
  }'
```

##### Response

```json
{ "code": 0, "message": "success" }
```
