
### `/collections/{collection_name}/indexes` (POST)

Updates the index type and nlist of a collection.

#### Request

<table>
<tr>
  <th>Request Component</th>
  <th>Value</th>
</tr>
<tr>
  <td> Name</td>
  <td><pre><code>/collections/{collection_name}/indexes</code></pre></td>
</tr>
<tr>
  <td>Header </td>
  <td><pre><code>accept: application/json</code></pre> </td>
</tr>
<tr>
  <td>Body</td>
  <td><pre><code>
  {
    "index_type": "IVFFLAT",
    "metric_type": "L2",
    "params": {
        "nlist": 16384
    }
  }
  </code></pre> </td>
</tr>
<tr>
  <td>Method</td>
  <td>POST</td>
</tr>

</table>

##### Body Parameters

| Parameter    | Description                                                                                                                                                                                              | Required? |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| `index_type` | The type of indexing method to query the collection. Please refer to [Milvus Indexes](https://www.milvus.io/docs/guides/index.md) for detailed introduction of supported indexes. The default is "FLAT". | No        |
| `metric_type`| The type of metric to query the collection. Please refer to [Milvus Indexes](https://www.milvus.io/docs/guides/index.md) for detailed introduction of supported indexes. The default is "FLAT". | No        |
| `params`     | The extra params of indexing method to query the collection. Please refer to [Index and search parameters](/#index-and-search-parameters) for detailed introduction of supported indexes.                                              | No        |

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
$ curl -X POST "http://127.0.0.1:19121/collections/test_collection/indexes" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "index_type": "IVFFLAT",
    "params": {
      "nlist":4096
    }
  }'
```

##### Response

```json
{ "message": "OK", "code": 0 }
```
