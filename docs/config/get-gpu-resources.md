
### `/config/gpu_resources` (GET)

Gets the parameter values in `gpu_resource_config` of the Milvus configuration file.

> Note: This method is available only for GPU-supported Milvus.

#### Request

| Request Component | Value                      |
| ----------------- | -------------------------- |
| Name              | `/config/gpu_resources`    |
| Header            | `accept: application/json` |
| Body              | N/A                        |
| Method            | GET                        |

#### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

#### Example

##### Request

```shell
$ curl -X GET "http://127.0.0.1:19121/config/gpu_resources" -H "accept: application/json"
```

##### Response

```json
{
  "enable": true,
  "cache_capacity": 1,
  "search_resources": ["GPU0"],
  "build_index_resources": ["GPU0"]
}
```