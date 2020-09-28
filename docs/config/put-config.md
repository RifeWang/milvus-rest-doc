
### `/config/advanced` (PUT)

Updates the values of parameters in `cache_config` and `engine_config` of the Milvus configuration file.

#### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/config/advanced</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "cpu_cache_capacity": integer($int64),
  "cache_insert_data": boolean,
  "use_blas_threshold": integer($int64),
  "gpu_search_threshold": integer($int64)
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>

</table>

> Note: `gpu_search_config` is available only in GPU-supported Milvus.

##### Body Parameters

| Parameter              | Description                                                                            | Required? |
| ---------------------- | -------------------------------------------------------------------------------------- | --------- |
| `cpu_cache_capacity`   | Value of `cpu_cache_capacity` in the Milvus configuration file. The default is 4.      | No        |
| `cache_insert_data`    | Value of `cache_insert_data` in the Milvus configuration file. The default is false.   | No        |
| `use_blas_threshold`   | Value of `use_blas_threshold` in the Milvus configuration file. The default is 1100.   | No        |
| `gpu_search_threshold` | Value of `gpu_search_threshold` in the Milvus configuration file. The default is 1000. | No        |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

#### Example

##### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/config/advanced" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "cpu_cache_capacity":4,
    "cache_insert_data":false,
    "use_blas_threshold":1100,
    "gpu_search_threshold":1000
  }'
```

##### Response

```json
{ "message": "OK", "code": 0 }
```
