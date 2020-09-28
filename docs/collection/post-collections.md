### `/collections` (POST)

Creates a collection.

#### Request

<table>
<tr>
  <th>Request Component</th>
  <th>Value</th>
</tr>
<tr>
  <td> Name</td>
  <td><pre><code>/collections</code></pre></td></tr>
<tr>
  <td>Header </td>
  <td><pre><code>accept: application/json</code></pre> </td></tr>
<tr>
  <td>Body</td>
  <td><code>
  {
      "collection_name":"test_collection",
      "dimension":1,
      "index_file_size":10,
      "metric_type":"L2"
  }
  </code></td>
</tr>
<tr>
  <td>Method
  </td><td>POST</td>
</tr>

</table>

##### Body Parameters

| Parameter         | Description                                                                               | Required? |
| ----------------- | ----------------------------------------------------------------------------------------- | --------- |
| `collection_name` | The name of the collection to create, which must be unique within its database.           | Yes       |
| `dimension` | The dimension of the vectors that are to be inserted into the created collection.         | Yes       |
| `index_file_size` | Threshold value that triggers index building for raw data files. The default is 1024.     | No        |
| `metric_type` | The method vector distances are compared in Milvus. The default is L2.                    | No        |

* Currently supported metrics include:
    - `L2` (Euclidean distance),
    - `IP` (Inner Product)
    - `HAMMING` (Hamming distance)
    - `JACCARD` (Jaccard distance)
    - `TANIMOTO` (Tanomoto distance)
    - `SUBSTRUCTURE` (Sub structure distance)
    - `SUPERSTRUCTURE` (Super structure distance)

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 201         | Created                                                           |
| 400         | The request is incorrect. Refer to the error message for details. |

#### Example

##### Request

``` shell
$ curl -X POST "http://127.0.0.1:19121/collections" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "collection_name":"test_collection",
    "dimension":1,
    "index_file_size":10,
    "metric_type":"L2"
  }'
```

##### Response

``` json
{ "message": "OK", "code": 0 }
```
