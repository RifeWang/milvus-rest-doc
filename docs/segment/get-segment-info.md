
### `/collections/{collection_name}/segments/{segment_name}/{info}` (GET)

Gets all vectors or ids of segment in a collection starting from `offset` and ends with `page_size`.

#### Request

| Request Component | Value                                     |
| ----------------- | ----------------------------------------- |
| Name              | `/collections/{collection_name}/segments/{segment_name}/{info}` |
| Header            | `accept: application/json`                |
| Body              | N/A                                       |
| Method            | GET                                       |

##### Query Parameters

| Parameter         | Description                                                   | Required? |
| ----------------- | ------------------------------------------------------------- | --------- |
| `collection_name` | Name of the collection.                                       | Yes       |
| `segment_name`    | Name of the segment.                                          | Yes       |
| `info`            | `vectors` or `ids`                                            | Yes       |
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
$ curl -X GET "http://127.0.0.1:19121/collections/test_collection/segments/1601265367773803000/ids?offset=0&page_size=1" -H "accept: application/json"
```

##### Response

```json
{
  "count": 16,
  "ids": [
      "1601265367344345000",
      "1601265367344345001",
      "1601265367344345002",
      "1601265367344345003",
      "1601264366389864000",
      "1601264366389864001",
      "1601264366389864002",
      "1601264366389864003",
      "1601263653227657000",
      "1601263653227657001"
  ]
}
```