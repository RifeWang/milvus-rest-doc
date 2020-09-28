### `/config/advanced` (GET)

Gets the values of parameters in `cache_config` and `engine_config` of the Milvus configuration file.

#### Request

| Request Component | Value                      |
| ----------------- | -------------------------- |
| Name              | `/config/advanced`         |
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
$ curl -X GET "http://127.0.0.1:19121/config/advanced" -H "accept: application/json"
```

##### Response

```json
{
  "cpu_cache_capacity": 4,
  "cache_insert_data": false,
  "use_blas_threshold": 1100,
  "gpu_search_threshold": 1000
}
```