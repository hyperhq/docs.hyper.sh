# Retrive logs of a function

`GET https://$region.hyperapp.io/$func/$uuid/logs`

Query realtime logs of a function.

**Example request**:

```
GET https://$region.hyperapp.io/helloworld/e5304888-f112-11e6-bc64-92361f002671/logs?request_id=7f713fff-a65c-4004-b195-72b0c7bce84a HTTP/1.1
```

**Example response**:

```
HTTP/1.1 101 UPGRADED
Connection: Upgrade
Upgrade: tcp

{"Time": "2017-01-06T15:47:31.485331387Z", "Event": "CALL", "CallId": "7f713fff-a65c-4004-b195-72b0c7bce84a", "ShortStdin": "Hello"}
{"Time": "2017-01-06T15:47:32.485331387Z", "Event": "PENDING", "CallId": "7f713fff-a65c-4004-b195-72b0c7bce84a"}
{"Time": "2017-01-06T15:47:33.485331387Z", "Event": "RUNNING", "CallId": "7f713fff-a65c-4004-b195-72b0c7bce84a"}
{"Time": "2017-01-06T15:47:45.485331387Z", "Event": "COMPLETED", "CallId": "7f713fff-a65c-4004-b195-72b0c7bce84a", "ShortStdout": "World"}
```

**URL parameters**:

* name - The function name.

**Query Parameters:**

- **request_id** - Filter logs of specific CallId. Default `all`.

**Status Codes**:

* 101 - no error
* 404 - no such func
* 500 - server error