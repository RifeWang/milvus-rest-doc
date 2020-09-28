
### `system/{op}` (PUT)

#### 1. Flush a collection

##### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/system/task</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "flush": {
     "collection_names": [$string]
  }
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>
</table>

##### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

##### Example

###### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/system/task" \
  -H "accept: application/json" \
  -d '{
    "flush": {
      "collection_names": ["test_collection"]
    }
  }'
```

###### Response

```json
{ "code": 0, "message": "success" }
```

#### 2. Compact segments in a collection

##### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/system/task</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "compact": {
     "collection_name": $string,
     "threshold": 0.1
  }
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>
</table>

##### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

##### Example

###### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/system/task" \
  -H "accept: application/json" \
  -d '{
    "compact": {
      "collection_name": "test_collection",
      "threshold": 0.1
    }
  }'
```

###### Response

```json
{ "code": 0, "message": "success" }
```

#### 3. Load a collection to memory

##### Request

<table>
<tr><th>Request Component</th><th>Value</th></tr>
<tr><td> Name</td><td><pre><code>/system/task</code></pre></td></tr>
<tr><td>Header </td><td><pre><code>accept: application/json</code></pre> </td></tr>
<tr><td>Body</td><td><pre><code>
{
  "load": {
     "collection_name": $string
  }
}
</code></pre> </td></tr>
<tr><td>Method</td><td>PUT</td></tr>
</table>

##### Response

| Status code | Description                                                       |
| ----------- | ----------------------------------------------------------------- |
| 200         | The request is successful.                                        |
| 400         | The request is incorrect. Refer to the error message for details. |

##### Example

###### Request

```shell
$ curl -X PUT "http://127.0.0.1:19121/system/task" \
  -H "accept: application/json" \
  -d '{
    "load": {
      "collection_name": "test_collection"
    }
  }'
```

###### Response

```json
{ "code": 0, "message": "success" }
```