### `/devices` (GET)

Gets CPU/GPU information from the host.

#### Request

| Request Component | Value                      |
| ----------------- | -------------------------- |
| Name              | `/devices`                 |
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
$ curl -X GET "http://127.0.0.1:19121/devices" -H "accept: application/json"
```

##### Response

```json
{
    "cpu": {
        "memory": 31
    },
    "gpus": {
        "GPU0": {
            "memory": 5
        }
    }
}
```