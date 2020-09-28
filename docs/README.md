
# Overview

[Milvus v0.10.3](https://github.com/milvus-io/milvus/blob/v0.10.3/core/src/server/web_impl/README.md)


With the RESTful API, you can use Milvus by sending HTTP requests to the Milvus server web port. The RESTful API is available as long as you have a running Milvus server. You can set the web port in the Milvus configuration file. Refer to [Milvus Configuration](https://www.milvus.io/docs/reference/milvus_config.md) for more information.



## Index and search parameters

For each index type, the RESTful API has specific index parameters and search parameters.

<table>
<tr><th>Index type</th><th>Create index param</th><th>Search param</th></tr>
<tr>
 <td> IVFFLAT</td>
 <td><pre><code>{"nlist": $int}</code></pre></td>
 <td><pre><code>{"nprobe": $int}</code></pre></td>
</tr>
<tr>
 <td> IVFPQ</td>
 <td><pre><code>{"m": $int, "nlist": $int}</code></pre></td>
 <td><pre><code>{"nprobe": $int}</code></pre></td>
</tr>
<tr>
 <td> IVFSQ8</td>
 <td><pre><code>{"nlist": $int}</code></pre></td>
 <td><pre><code>{"nprobe": $int}</code></pre></td>
</tr>
<tr>
 <td> IVFSQ8H</td>
 <td><pre><code>{"nlist": $int}</code></pre></td>
 <td><pre><code>{"nprobe": $int}</code></pre></td>
</tr>
<tr>
 <td> HNSW</td>
 <td><pre><code>{"M": $int, "efConstruction": $int}</code></pre></td>
 <td><pre><code>{"ef": $int}</code></pre></td>
</tr>
<tr>
 <td> ANNOY</td>
 <td><pre><code>{"n_trees": $int}</code></pre></td>
 <td><pre><code>{"search_k": $int}</code></pre></td>
</tr>
</table>

For detailed information about the parameters above, refer to [Milvus Indexes](https://milvus.io/docs/guides/index.md)

## Error Codes

The RESTful API returns error messages as JSON text. Each type of error message has a specific error code.

| Type                  | Code |
| --------------------- | ---- |
| SUCCESS               | 0    |
| UNEXPECTED_ERROR      | 1    |
| CONNECT_FAILED        | 2    |
| PERMISSION_DENIED     | 3    |
| TABLE_NOT_EXISTS      | 4    |
| ILLEGAL_ARGUMENT      | 5    |
| ILLEGAL_RANGE         | 6    |
| ILLEGAL_DIMENSION     | 7    |
| ILLEGAL_INDEX_TYPE    | 8    |
| ILLEGAL_TABLE_NAME    | 9    |
| ILLEGAL_TOPK          | 10   |
| ILLEGAL_ROWRECORD     | 11   |
| ILLEGAL_VECTOR_ID     | 12   |
| ILLEGAL_SEARCH_RESULT | 13   |
| FILE_NOT_FOUND        | 14   |
| META_FAILED           | 15   |
| CACHE_FAILED          | 16   |
| CANNOT_CREATE_FOLDER  | 17   |
| CANNOT_CREATE_FILE    | 18   |
| CANNOT_DELETE_FOLDER  | 19   |
| CANNOT_DELETE_FILE    | 20   |
| BUILD_INDEX_ERROR     | 21   |
| ILLEGAL_NLIST         | 22   |
| ILLEGAL_METRIC_TYPE   | 23   |
| OUT_OF_MEMORY         | 24   |
| PATH_PARAM_LOSS       | 31   |
| UNKNOWN_PATH          | 32   |
| QUERY_PARAM_LOSS      | 33   |
| BODY_FIELD_LOSS       | 34   |
| ILLEGAL_BODY          | 35   |
| BODY_PARSE_FAIL       | 36   |
| ILLEGAL_QUERY_PARAM   | 37   |
