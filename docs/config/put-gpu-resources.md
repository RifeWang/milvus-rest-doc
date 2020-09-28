
### `/config/gpu_resources` (PUT)

Updates the parameter values in `gpu_resource_config` of the Milvus configuration file.

> Note: This method is available only for GPU-supported Milvus.

#### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/config/gpu_resources</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "enable": boolean,
  "cache_capacity": integer($int64),
  "search_resources": [string],
  "build_index_resources": [string]
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>

</table>

##### Body Parameters

| Parameter               | Description                                                        | Required? |
| ----------------------- | ------------------------------------------------------------------ | --------- |
| `enable`                | Specifies whether to enable GPU resources.                         | Yes       |
| `cache_capacity`        | Size of GPU memory per card used for cache in GBs.                 | Yes       |
| `search_resources`      | GPU devices used for search computation, must be in format `gpux`. | Yes       |
| `build_index_resources` | GPU devices used for index building, must be in format `gpux`.     | Yes       |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

#### Example

##### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/config/gpu_resources" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{
    "enable":true,
    "cache_capacity":1,
    "search_resources":["GPU0"],
    "build_index_resources":["GPU0"]
  }'
```

##### Response

```json
{ "message": "OK", "code": 0 }
```
