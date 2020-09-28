
### `/collections/{collection_name}` (GET)

Gets all information about a collection by name.

#### Request

| Request Component | Value                            |
| ----------------- | -------------------------------- |
| Name              | `/collections/{collection_name}` |
| Header            | `accept: application/json`       |
| Body              | N/A                              |
| Method            | GET                              |

##### Query Parameters

| Parameter         | Description                                                                                                                                                                                                                                                                                                               | Required? |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| `collection_name` | Name of the collection.                                                                                                                                                                                                                                                                                                   | Yes       |
| `info`            | Type of information to acquire. `info` must either be empty or `stat`. When `info` is empty, Milvus returns collection name, dimension, index file size, metric type, offset, index type, and nlist of the collection. When `info` is `stat`, Milvus returns the collection offset, partition status, and segment status. | No        |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The required resource does not exist.                             |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/collections/test_collection" -H "accept: application/json"
```

##### Response

```json
{
    "collection_name": "test_collection",
    "count": 0,
    "dimension": 1,
    "index": "IVFFLAT",
    "index_file_size": 10,
    "index_params": "{\"nlist\":16384}",
    "metric_type": "L2"
}
```

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/collections/test_collection?info=stat" -H "accept: application/json"
```

##### Response

```json
{
  "partitions":[
    {
      "row_count":10000,
      "segments":[
        {
          "data_size":5284922,
          "index_name":"IVFFLAT",
          "name":"1589468453228582000",
          "row_count":10000
        }
      ],
      "tag":"_default"
    }
  ],
  "row_count":10000
}

```
