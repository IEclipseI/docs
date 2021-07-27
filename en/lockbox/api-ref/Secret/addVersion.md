---
editable: false

__system: {"dislikeVariants":["No answer to my question","Recomendations didn't help","The content doesn't match title","Other"]}
---


# Method addVersion
Adds new version based on a previous one.
 

 
## HTTP request {#https-request}
```
POST https://lockbox.api.cloud.yandex.net/lockbox/v1/secrets/{secretId}:addVersion
```
 
## Path parameters {#path_params}
 
Parameter | Description
--- | ---
secretId | Required. ID of the secret.  The maximum string length in characters is 50.
 
## Body parameters {#body_params}
 
```json 
{
  "description": "string",
  "payloadEntries": [
    {
      "key": "string",

      // `payloadEntries[]` includes only one of the fields `textValue`, `binaryValue`
      "textValue": "string",
      "binaryValue": "string",
      // end of the list of possible fields`payloadEntries[]`

    }
  ],
  "baseVersionId": "string"
}
```

 
Field | Description
--- | ---
description | **string**<br><p>Description of the version.</p> <p>The maximum string length in characters is 1024.</p> 
payloadEntries[] | **object**<br><p>Describe how payload entries of the base version change in the added version.</p> <p>The maximum number of elements is 32.</p> 
payloadEntries[].<br>key | **string**<br><p>Required. Non-confidential key of the entry.</p> <p>The maximum string length in characters is 256. Value must match the regular expression ``[.-_0-9a-zA-Z]+``.</p> 
payloadEntries[].<br>textValue | **string** <br>`payloadEntries[]` includes only one of the fields `textValue`, `binaryValue`<br><br><p>Use the field to set a text value.</p> <p>The maximum string length in characters is 65536.</p> 
payloadEntries[].<br>binaryValue | **string** (byte) <br>`payloadEntries[]` includes only one of the fields `textValue`, `binaryValue`<br><br><p>Use the field to set a binary value.</p> <p>The maximum string length in characters is 65536.</p> 
baseVersionId | **string**<br><p>Optional base version id. Defaults to the current version if not specified</p> <p>The maximum string length in characters is 50.</p> 
 
## Response {#responses}
**HTTP Code: 200 - OK**

```json 
{
  "id": "string",
  "description": "string",
  "createdAt": "string",
  "createdBy": "string",
  "modifiedAt": "string",
  "done": true,
  "metadata": "object",

  //  includes only one of the fields `error`, `response`
  "error": {
    "code": "integer",
    "message": "string",
    "details": [
      "object"
    ]
  },
  "response": "object",
  // end of the list of possible fields

}
```
An Operation resource. For more information, see [Operation](/docs/api-design-guide/concepts/operation).
 
Field | Description
--- | ---
id | **string**<br><p>ID of the operation.</p> 
description | **string**<br><p>Description of the operation. 0-256 characters long.</p> 
createdAt | **string** (date-time)<br><p>Creation timestamp.</p> <p>String in <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a> text format.</p> 
createdBy | **string**<br><p>ID of the user or service account who initiated the operation.</p> 
modifiedAt | **string** (date-time)<br><p>The time when the Operation resource was last modified.</p> <p>String in <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a> text format.</p> 
done | **boolean** (boolean)<br><p>If the value is ``false``, it means the operation is still in progress. If ``true``, the operation is completed, and either ``error`` or ``response`` is available.</p> 
metadata | **object**<br><p>Service-specific metadata associated with the operation. It typically contains the ID of the target resource that the operation is performed on. Any method that returns a long-running operation should document the metadata type, if any.</p> 
error | **object**<br>The error result of the operation in case of failure or cancellation. <br> includes only one of the fields `error`, `response`<br><br><p>The error result of the operation in case of failure or cancellation.</p> 
error.<br>code | **integer** (int32)<br><p>Error code. An enum value of <a href="https://github.com/googleapis/googleapis/blob/master/google/rpc/code.proto">google.rpc.Code</a>.</p> 
error.<br>message | **string**<br><p>An error message.</p> 
error.<br>details[] | **object**<br><p>A list of messages that carry the error details.</p> 
response | **object** <br> includes only one of the fields `error`, `response`<br><br><p>The normal response of the operation in case of success. If the original method returns no data on success, such as Delete, the response is <a href="https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#empty">google.protobuf.Empty</a>. If the original method is the standard Create/Update, the response should be the target resource of the operation. Any method that returns a long-running operation should document the response type, if any.</p> 