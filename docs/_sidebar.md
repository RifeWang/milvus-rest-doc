<!-- docs/_sidebar.md -->

* [Overview](/)

* cat
  * [GET /state](cat/get-state)
  * [GET /devices](cat/get-devices)
* config
  * [GET /config/advanced](config/get-config)
  * [PUT /config/advanced](config/put-config)
  * [OPTIONS /config/advanced](config/options-config)
  * [GET /config/gpu_resources](config/get-gpu-resources)
  * [PUT /config/gpu_resources](config/put-gpu-resources)
  * [OPTIONS /config/gpu_resources](config/options-gpu-resources)
* collection
  * [GET /collections](collection/get-collections)
  * [POST /collections](collection/post-collections)
  * [OPTIONS /collections](collection/options-collections)
  * [GET /collections/{collection_name}](collection/get-collections-collection_name)
  * [DELETE /collections/{collection_name}](collection/delete-collections-collection_name)
  * [OPTIONS /collections/{collection_name}](collection/options-collections-collection_name)
* index
  * [POST /collections/{collection_name}/indexes](index/post-index)
  * [DELETE /collections/{collection_name}/indexes](index/delete-index)
  * [OPTIONS /collections/{collection_name}/indexes](index/options-index)
* partition
  * [GET /collections/{collection_name}/partitions](partition/get-partitions)
  * [POST /collections/{collection_name}/partitions](partition/post-partitions)
  * [OPTIONS /collections/{collection_name}/partitions](partition/options-partitions)
  * [DELETE /collections/{collection_name}/partitions](partition/delete-partitions)
* segment
  * [GET /collections/{collection_name}/segments](segment/get-segments)
  * [GET /collections/{collection_name}/segments/{segment_name}/{info}](segment/get-segment-info)
* entity
  * [GET /collections/{collection_name}/vectors](entity/get-vectors)
  * [POST /collections/{collection_name}/vectors](entity/post-vectors)
  * [PUT /collections/{collection_name}/vectors](entity/put-vectors)
  * [OPTIONS /collections/{collection_name}/vectors](entity/options-vectors)
* system
  * [GET /system/{msg}](system/get-system)
  * [PUT /system/{op}](system/put-system)
