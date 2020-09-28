
### `/collections/{collection_name}/partitions` (DELETE)

Deletes a partition by tag.

#### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/collections/{collection_name}/partitions</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "partition_tag": string
}
</code></pre> </td></tr>
<tr><td>Method</td><td>DELETE</td></tr>

</table>

##### Query Parameters

| Parameter         | Description                                         | Required? |
| ----------------- | --------------------------------------------------- | --------- |
| `collection_name` | Name of the collection that contains the partition. | Yes       |
| `partition_tag`   | Tag of the partition to delete.                     | yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 204         | Deleted                                                           |
| 400         | The request is incorrect. Refer to the error message for details. |
| 404         | The requested resource does not exist.                            |

#### Example

##### Request

```shell
$ curl -X DELETE "http://127.0.0.1:19121/collections/test_collection/partitions" \
  -H "accept: application/json" \
  -d '{"partition_tag": "tags_01"}'
```

The deletion is successful if no information is returned.
