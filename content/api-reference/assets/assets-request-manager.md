---
uid: assets-request-manager

---

# Request Manager
The asset type API provides methods to create, read, update, and delete asset types.An asset type can be used to build many similar assets.Some of the key benefits of using an asset type as the base model for assets are: - Multiple similar assets can be created more quickly and with less effort. - Maintaining assets is simplified...

## `List Assets`

<a id="opIdRequestManager_List Assets"></a>

Gets Assets in a given namespace.

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets
?skip={skip}&count={count}&orderBy={orderBy}&query={query}&pageSize={pageSize}&maxPages={maxPages}&continuationToken={continuationToken}&Comparer={Comparer}&Count={Count}&Keys={Keys}&System.Collections.Generic.IDictionary<TKey,TValue>.Keys={System.Collections.Generic.IDictionary<TKey,TValue>.Keys}&System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys={System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys}&Values={Values}&System.Collections.Generic.IDictionary<TKey,TValue>.Values={System.Collections.Generic.IDictionary<TKey,TValue>.Values}&System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values={System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values}&Item={Item}&System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly={System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly}&System.Collections.ICollection.IsSynchronized={System.Collections.ICollection.IsSynchronized}&System.Collections.ICollection.SyncRoot={System.Collections.ICollection.SyncRoot}&System.Collections.IDictionary.IsFixedSize={System.Collections.IDictionary.IsFixedSize}&System.Collections.IDictionary.IsReadOnly={System.Collections.IDictionary.IsReadOnly}&System.Collections.IDictionary.Keys={System.Collections.IDictionary.Keys}&System.Collections.IDictionary.Values={System.Collections.IDictionary.Values}&System.Collections.IDictionary.Item={System.Collections.IDictionary.Item}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/>Skip.<br/><br/>`[optional] integer count`
<br/>Count.<br/><br/>`[optional] string orderBy`
<br/><br/>`[optional] string query`
<br/><br/>`[optional] integer pageSize`
<br/><br/>`[optional] integer maxPages`
<br/><br/>`[optional] string continuationToken`
<br/><br/>`[optional] object Comparer`
<br/><br/>`[optional] integer Count`
<br/><br/>`[optional] array Keys`
<br/><br/>`[optional] array System.Collections.Generic.IDictionary<TKey,TValue>.Keys`
<br/><br/>`[optional] array System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys`
<br/><br/>`[optional] array Values`
<br/><br/>`[optional] array System.Collections.Generic.IDictionary<TKey,TValue>.Values`
<br/><br/>`[optional] array System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values`
<br/><br/>`[optional] array Item`
<br/><br/>`[optional] boolean System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly`
<br/><br/>`[optional] boolean System.Collections.ICollection.IsSynchronized`
<br/><br/>`[optional] any System.Collections.ICollection.SyncRoot`
<br/><br/>`[optional] boolean System.Collections.IDictionary.IsFixedSize`
<br/><br/>`[optional] boolean System.Collections.IDictionary.IsReadOnly`
<br/><br/>`[optional] array System.Collections.IDictionary.Keys`
<br/><br/>`[optional] array System.Collections.IDictionary.Values`
<br/><br/>`[optional] any System.Collections.IDictionary.Item`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeprecatedAsset](#schemadeprecatedasset)[]|List of assets in the given namespace.|
|400|[ErrorTemplate](#schemaerrortemplate)|The request is not valid. See the response body for additional details.|
|401|None|Unauthorized.|
|500|None|Internal Service Error, please try again later.|
|503|None|Service Unavaiable, please try again later.|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|Total number of sers in the Tenant.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "Heater_HIJK",
    "Name": "HeaterOnFirstFloor",
    "Description": "This is Asset which represents a heater on the first floor."
  },
  {
    "Id": "Heater_ABCDEF",
    "Name": "HeaterOnFirstFloor",
    "Description": "This is Asset which represents a heater on the first floor."
  }
]
```

> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Resolution": "string",
  "Reason": "string",
  "property1": null,
  "property2": null
}
```

---

## `Create Asset`

<a id="opIdRequestManager_Create Asset"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {}
    ]
  }
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeprecatedAsset](#schemadeprecatedasset)|None|
|302|None|None|
|400|[ErrorTemplate](#schemaerrortemplate)|None|
|403|None|None|
|409|None|None|
|500|None|None|
|503|None|None|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {
        "Value": null,
        "Status": "[",
        "DisplayName": "string"
      }
    ]
  }
}
```

---

## `Get Assets Async2`

<a id="opIdRequestManager_Get Assets Async2"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets2
?skip={skip}&count={count}&orderBy={orderBy}&query={query}&pageSize={pageSize}&maxPages={maxPages}&continuationToken={continuationToken}&Comparer={Comparer}&Count={Count}&Keys={Keys}&System.Collections.Generic.IDictionary<TKey,TValue>.Keys={System.Collections.Generic.IDictionary<TKey,TValue>.Keys}&System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys={System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys}&Values={Values}&System.Collections.Generic.IDictionary<TKey,TValue>.Values={System.Collections.Generic.IDictionary<TKey,TValue>.Values}&System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values={System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values}&Item={Item}&System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly={System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly}&System.Collections.ICollection.IsSynchronized={System.Collections.ICollection.IsSynchronized}&System.Collections.ICollection.SyncRoot={System.Collections.ICollection.SyncRoot}&System.Collections.IDictionary.IsFixedSize={System.Collections.IDictionary.IsFixedSize}&System.Collections.IDictionary.IsReadOnly={System.Collections.IDictionary.IsReadOnly}&System.Collections.IDictionary.Keys={System.Collections.IDictionary.Keys}&System.Collections.IDictionary.Values={System.Collections.IDictionary.Values}&System.Collections.IDictionary.Item={System.Collections.IDictionary.Item}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>`[optional] string orderBy`
<br/><br/>`[optional] string query`
<br/><br/>`[optional] integer pageSize`
<br/><br/>`[optional] integer maxPages`
<br/><br/>`[optional] string continuationToken`
<br/><br/>`[optional] object Comparer`
<br/><br/>`[optional] integer Count`
<br/><br/>`[optional] array Keys`
<br/><br/>`[optional] array System.Collections.Generic.IDictionary<TKey,TValue>.Keys`
<br/><br/>`[optional] array System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys`
<br/><br/>`[optional] array Values`
<br/><br/>`[optional] array System.Collections.Generic.IDictionary<TKey,TValue>.Values`
<br/><br/>`[optional] array System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values`
<br/><br/>`[optional] array Item`
<br/><br/>`[optional] boolean System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly`
<br/><br/>`[optional] boolean System.Collections.ICollection.IsSynchronized`
<br/><br/>`[optional] any System.Collections.ICollection.SyncRoot`
<br/><br/>`[optional] boolean System.Collections.IDictionary.IsFixedSize`
<br/><br/>`[optional] boolean System.Collections.IDictionary.IsReadOnly`
<br/><br/>`[optional] array System.Collections.IDictionary.Keys`
<br/><br/>`[optional] array System.Collections.IDictionary.Values`
<br/><br/>`[optional] any System.Collections.IDictionary.Item`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Create Asset Async2`

<a id="opIdRequestManager_Create Asset Async2"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets2
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "DefinitionType": 0,
    "Definition": null
  }
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Bulk Create Assets`

<a id="opIdRequestManager_Bulk Create Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets
```

#### Parameters

`string tenantId`
<br/>The tenant identifier.<br/><br/>`string namespaceId`
<br/>The namespace identifier.<br/><br/>

### Request Body

<br/>

```json
[
  {
    "Id": "string",
    "AssetTypeId": "string",
    "Name": "string",
    "Description": "string",
    "Metadata": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "SdsTypeCode": "Empty",
        "Value": null,
        "Uom": "string"
      }
    ],
    "StreamReferences": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "StreamId": "string"
      }
    ],
    "Status": {
      "StreamReferenceId": "string",
      "StreamPropertyId": "string",
      "ValueStatusMappings": [
        {
          "Value": null,
          "Status": null,
          "DisplayName": null
        }
      ]
    }
  }
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Bulk Delete Assets`

<a id="opIdRequestManager_Bulk Delete Assets"></a>

### Request
```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets
?id={id}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] array id`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Bulk Deprecated Get Resolved Assets`

<a id="opIdRequestManager_Bulk Deprecated Get Resolved Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/resolved
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
[
  "string"
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Bulk Get Resolved Assets`

<a id="opIdRequestManager_Bulk Get Resolved Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/resolved2
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
[
  "string"
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Get Bulk Last Status Data For Assets`

<a id="opIdRequestManager_Get Bulk Last Status Data For Assets"></a>

View the status of multiple assets.

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/status/last
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>

### Request Body

The assets identifiers you are interested in.<br/>

```json
[
  "AssetId-1",
  "AssetId-2",
  "AssetId-3"
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[LastStatusData](#schemalaststatusdata)[]|The last status of assets in the POST body.|
|207|[MultiStatusResultOfLastStatusDataAndChildErrorTemplate](#schemamultistatusresultoflaststatusdataandchilderrortemplate)|On POST, returns the status of multiple assets. For error responses, check the multi-status response for the error and cause.|
|400|[ErrorTemplate](#schemaerrortemplate)|The request is not valid. See the response body for additional details.|
|500|None|Internal Service Error, please try again later..|
|503|None|Service Unavaiable, please try again later..|

#### Example response body
> 200 Response

```json
[
  {
    "AssetId": "AssetId-1",
    "Status": 1,
    "Value": "85",
    "DisplayName": "TemperatureSensorBuild1InF",
    "DataRetrievalTime": "2020-05-04T16:55:26.3732693Z"
  },
  {
    "AssetId": "AssetId-2",
    "Status": 2,
    "Value": "185",
    "DisplayName": "DeviceMeasurement",
    "DataRetrievalTime": "2020-05-04T16:55:26.3732693Z"
  }
]
```

> 207 Response

```json
{
  "Reason": "string",
  "Error": "string",
  "OperationId": "string",
  "Data": [
    {
      "Index": null,
      "Status": 0,
      "Value": null,
      "DisplayName": "string",
      "AssetId": "string",
      "DataRetrievalTime": "2019-08-24T14:15:22Z"
    }
  ],
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Resolution": "string",
      "Reason": "string",
      "StatusCode": 0,
      "property1": null,
      "property2": null
    }
  ]
}
```

---

## `Bulk Create Assets Async2`

<a id="opIdRequestManager_Bulk Create Assets Async2"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets2
```

#### Parameters

`string tenantId`
<br/>The tenant identifier.<br/><br/>`string namespaceId`
<br/>The namespace identifier.<br/><br/>

### Request Body

<br/>

```json
[
  {
    "Id": "string",
    "AssetTypeId": "string",
    "Name": "string",
    "Description": "string",
    "Metadata": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "SdsTypeCode": "Empty",
        "Value": null,
        "Uom": "string"
      }
    ],
    "StreamReferences": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "StreamId": "string"
      }
    ],
    "Status": {
      "DefinitionType": 0,
      "Definition": null
    }
  }
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Get Assets In Search Result Format`

<a id="opIdRequestManager_Get Assets In Search Result Format"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/search/assets
?skip={skip}&count={count}&orderBy={orderBy}&query={query}&pageSize={pageSize}&maxPages={maxPages}&continuationToken={continuationToken}&Comparer={Comparer}&Count={Count}&Keys={Keys}&System.Collections.Generic.IDictionary<TKey,TValue>.Keys={System.Collections.Generic.IDictionary<TKey,TValue>.Keys}&System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys={System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys}&Values={Values}&System.Collections.Generic.IDictionary<TKey,TValue>.Values={System.Collections.Generic.IDictionary<TKey,TValue>.Values}&System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values={System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values}&Item={Item}&System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly={System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly}&System.Collections.ICollection.IsSynchronized={System.Collections.ICollection.IsSynchronized}&System.Collections.ICollection.SyncRoot={System.Collections.ICollection.SyncRoot}&System.Collections.IDictionary.IsFixedSize={System.Collections.IDictionary.IsFixedSize}&System.Collections.IDictionary.IsReadOnly={System.Collections.IDictionary.IsReadOnly}&System.Collections.IDictionary.Keys={System.Collections.IDictionary.Keys}&System.Collections.IDictionary.Values={System.Collections.IDictionary.Values}&System.Collections.IDictionary.Item={System.Collections.IDictionary.Item}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>`[optional] string orderBy`
<br/><br/>`[optional] string query`
<br/><br/>`[optional] integer pageSize`
<br/><br/>`[optional] integer maxPages`
<br/><br/>`[optional] string continuationToken`
<br/><br/>`[optional] object Comparer`
<br/><br/>`[optional] integer Count`
<br/><br/>`[optional] array Keys`
<br/><br/>`[optional] array System.Collections.Generic.IDictionary<TKey,TValue>.Keys`
<br/><br/>`[optional] array System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Keys`
<br/><br/>`[optional] array Values`
<br/><br/>`[optional] array System.Collections.Generic.IDictionary<TKey,TValue>.Values`
<br/><br/>`[optional] array System.Collections.Generic.IReadOnlyDictionary<TKey,TValue>.Values`
<br/><br/>`[optional] array Item`
<br/><br/>`[optional] boolean System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.IsReadOnly`
<br/><br/>`[optional] boolean System.Collections.ICollection.IsSynchronized`
<br/><br/>`[optional] any System.Collections.ICollection.SyncRoot`
<br/><br/>`[optional] boolean System.Collections.IDictionary.IsFixedSize`
<br/><br/>`[optional] boolean System.Collections.IDictionary.IsReadOnly`
<br/><br/>`[optional] array System.Collections.IDictionary.Keys`
<br/><br/>`[optional] array System.Collections.IDictionary.Values`
<br/><br/>`[optional] any System.Collections.IDictionary.Item`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Get Autocomplete Results`

<a id="opIdRequestManager_Get Autocomplete Results"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/search/assets/autocomplete
?term={term}&termCount={termCount}&facetCount={facetCount}
```

#### Parameters

`string term`
<br/><br/>`integer termCount`
<br/><br/>`integer facetCount`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Get Faceted Search Results`

<a id="opIdRequestManager_Get Faceted Search Results"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/search/assets/facets
?count={count}&name={name}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer count`
<br/><br/>`[optional] string name`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Definitions

### Asset

<a id="schemaasset"></a>
<a id="schema_Asset"></a>
<a id="tocSasset"></a>
<a id="tocsasset"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|AssetTypeId|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|Metadata|[[MetadataItem](#schemametadataitem)]|false|true|None|
|StreamReferences|[[StreamReference](#schemastreamreference)]|false|true|None|
|Status|[StatusConfiguration](#schemastatusconfiguration)|false|true|None|

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "DefinitionType": 0,
    "Definition": null
  }
}

```

---

### MetadataItem

<a id="schemametadataitem"></a>
<a id="schema_MetadataItem"></a>
<a id="tocSmetadataitem"></a>
<a id="tocsmetadataitem"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|SdsTypeCode|[SdsTypeCode2](#schemasdstypecode2)|false|false|None|
|Value|any|false|true|None|
|Uom|string|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "SdsTypeCode": "Empty",
  "Value": null,
  "Uom": "string"
}

```

---

### SdsTypeCode

<a id="schemasdstypecode"></a>
<a id="schema_SdsTypeCode"></a>
<a id="tocSsdstypecode"></a>
<a id="tocssdstypecode"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Empty|0|
|Object|1|
|Boolean|3|
|Char|4|
|SByte|5|
|Byte|6|
|Int16|7|
|UInt16|8|
|Int32|9|
|UInt32|10|
|Int64|11|
|UInt64|12|
|Single|13|
|Double|14|
|Decimal|15|
|DateTime|16|
|String|18|
|Guid|19|
|DateTimeOffset|20|
|TimeSpan|21|
|Version|22|
|NullableBoolean|103|
|NullableChar|104|
|NullableSByte|105|
|NullableByte|106|
|NullableInt16|107|
|NullableUInt16|108|
|NullableInt32|109|
|NullableUInt32|110|
|NullableInt64|111|
|NullableUInt64|112|
|NullableSingle|113|
|NullableDouble|114|
|NullableDecimal|115|
|NullableDateTime|116|
|NullableGuid|119|
|NullableDateTimeOffset|120|
|NullableTimeSpan|121|
|BooleanArray|203|
|CharArray|204|
|SByteArray|205|
|ByteArray|206|
|Int16Array|207|
|UInt16Array|208|
|Int32Array|209|
|UInt32Array|210|
|Int64Array|211|
|UInt64Array|212|
|SingleArray|213|
|DoubleArray|214|
|DecimalArray|215|
|DateTimeArray|216|
|StringArray|218|
|GuidArray|219|
|DateTimeOffsetArray|220|
|TimeSpanArray|221|
|VersionArray|222|
|Array|400|
|IList|401|
|IDictionary|402|
|IEnumerable|403|
|SdsType|501|
|SdsTypeProperty|502|
|SdsStreamView|503|
|SdsStreamViewProperty|504|
|SdsStreamViewMap|505|
|SdsStreamViewMapProperty|506|
|SdsStream|507|
|SdsStreamIndex|508|
|SdsTable|509|
|SdsColumn|510|
|SdsValues|511|
|SdsObject|512|
|SByteEnum|605|
|ByteEnum|606|
|Int16Enum|607|
|UInt16Enum|608|
|Int32Enum|609|
|UInt32Enum|610|
|Int64Enum|611|
|UInt64Enum|612|
|NullableSByteEnum|705|
|NullableByteEnum|706|
|NullableInt16Enum|707|
|NullableUInt16Enum|708|
|NullableInt32Enum|709|
|NullableUInt32Enum|710|
|NullableInt64Enum|711|
|NullableUInt64Enum|712|

---

### SdsTypeCode2

<a id="schemasdstypecode2"></a>
<a id="schema_SdsTypeCode2"></a>
<a id="tocSsdstypecode2"></a>
<a id="tocssdstypecode2"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Empty|Empty|
|Object|Object|
|Boolean|Boolean|
|Char|Char|
|SByte|SByte|
|Byte|Byte|
|Int16|Int16|
|UInt16|UInt16|
|Int32|Int32|
|UInt32|UInt32|
|Int64|Int64|
|UInt64|UInt64|
|Single|Single|
|Double|Double|
|Decimal|Decimal|
|DateTime|DateTime|
|String|String|
|Guid|Guid|
|DateTimeOffset|DateTimeOffset|
|TimeSpan|TimeSpan|
|Version|Version|
|NullableBoolean|NullableBoolean|
|NullableChar|NullableChar|
|NullableSByte|NullableSByte|
|NullableByte|NullableByte|
|NullableInt16|NullableInt16|
|NullableUInt16|NullableUInt16|
|NullableInt32|NullableInt32|
|NullableUInt32|NullableUInt32|
|NullableInt64|NullableInt64|
|NullableUInt64|NullableUInt64|
|NullableSingle|NullableSingle|
|NullableDouble|NullableDouble|
|NullableDecimal|NullableDecimal|
|NullableDateTime|NullableDateTime|
|NullableGuid|NullableGuid|
|NullableDateTimeOffset|NullableDateTimeOffset|
|NullableTimeSpan|NullableTimeSpan|
|BooleanArray|BooleanArray|
|CharArray|CharArray|
|SByteArray|SByteArray|
|ByteArray|ByteArray|
|Int16Array|Int16Array|
|UInt16Array|UInt16Array|
|Int32Array|Int32Array|
|UInt32Array|UInt32Array|
|Int64Array|Int64Array|
|UInt64Array|UInt64Array|
|SingleArray|SingleArray|
|DoubleArray|DoubleArray|
|DecimalArray|DecimalArray|
|DateTimeArray|DateTimeArray|
|StringArray|StringArray|
|GuidArray|GuidArray|
|DateTimeOffsetArray|DateTimeOffsetArray|
|TimeSpanArray|TimeSpanArray|
|VersionArray|VersionArray|
|Array|Array|
|IList|IList|
|IDictionary|IDictionary|
|IEnumerable|IEnumerable|
|SdsType|SdsType|
|SdsTypeProperty|SdsTypeProperty|
|SdsStreamView|SdsStreamView|
|SdsStreamViewProperty|SdsStreamViewProperty|
|SdsStreamViewMap|SdsStreamViewMap|
|SdsStreamViewMapProperty|SdsStreamViewMapProperty|
|SdsStream|SdsStream|
|SdsStreamIndex|SdsStreamIndex|
|SdsTable|SdsTable|
|SdsColumn|SdsColumn|
|SdsValues|SdsValues|
|SdsObject|SdsObject|
|SByteEnum|SByteEnum|
|ByteEnum|ByteEnum|
|Int16Enum|Int16Enum|
|UInt16Enum|UInt16Enum|
|Int32Enum|Int32Enum|
|UInt32Enum|UInt32Enum|
|Int64Enum|Int64Enum|
|UInt64Enum|UInt64Enum|
|NullableSByteEnum|NullableSByteEnum|
|NullableByteEnum|NullableByteEnum|
|NullableInt16Enum|NullableInt16Enum|
|NullableUInt16Enum|NullableUInt16Enum|
|NullableInt32Enum|NullableInt32Enum|
|NullableUInt32Enum|NullableUInt32Enum|
|NullableInt64Enum|NullableInt64Enum|
|NullableUInt64Enum|NullableUInt64Enum|

---

### StreamReference

<a id="schemastreamreference"></a>
<a id="schema_StreamReference"></a>
<a id="tocSstreamreference"></a>
<a id="tocsstreamreference"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|StreamId|string|true|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "StreamId": "string"
}

```

---

### StatusConfiguration

<a id="schemastatusconfiguration"></a>
<a id="schema_StatusConfiguration"></a>
<a id="tocSstatusconfiguration"></a>
<a id="tocsstatusconfiguration"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|DefinitionType|[StatusDefinitionType](#schemastatusdefinitiontype)|false|false|None|
|Definition|any|false|true|None|

```json
{
  "DefinitionType": 0,
  "Definition": null
}

```

---

### StatusDefinitionType

<a id="schemastatusdefinitiontype"></a>
<a id="schema_StatusDefinitionType"></a>
<a id="tocSstatusdefinitiontype"></a>
<a id="tocsstatusdefinitiontype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Unspecified|0|
|StreamPropertyMapping|1|

---

### DeprecatedAsset

<a id="schemadeprecatedasset"></a>
<a id="schema_DeprecatedAsset"></a>
<a id="tocSdeprecatedasset"></a>
<a id="tocsdeprecatedasset"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|AssetTypeId|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|Metadata|[[MetadataItem](#schemametadataitem)]|false|true|None|
|StreamReferences|[[StreamReference](#schemastreamreference)]|false|true|None|
|Status|[StatusMapping](#schemastatusmapping)|false|true|None|

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {
        "Value": null,
        "Status": "[",
        "DisplayName": "string"
      }
    ]
  }
}

```

---

### StatusMapping

<a id="schemastatusmapping"></a>
<a id="schema_StatusMapping"></a>
<a id="tocSstatusmapping"></a>
<a id="tocsstatusmapping"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamReferenceId|string|true|false|None|
|StreamPropertyId|string|true|false|None|
|ValueStatusMappings|[[ValueStatusMapping](#schemavaluestatusmapping)]|false|true|None|

```json
{
  "StreamReferenceId": "string",
  "StreamPropertyId": "string",
  "ValueStatusMappings": [
    {
      "Value": null,
      "Status": 0,
      "DisplayName": "string"
    }
  ]
}

```

---

### ValueStatusMapping

<a id="schemavaluestatusmapping"></a>
<a id="schema_ValueStatusMapping"></a>
<a id="tocSvaluestatusmapping"></a>
<a id="tocsvaluestatusmapping"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|any|false|true|None|
|Status|[StatusEnum](#schemastatusenum)|true|false|None|
|DisplayName|string|false|true|None|

```json
{
  "Value": null,
  "Status": 0,
  "DisplayName": "string"
}

```

---

### StatusEnum

<a id="schemastatusenum"></a>
<a id="schema_StatusEnum"></a>
<a id="tocSstatusenum"></a>
<a id="tocsstatusenum"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Unknown|0|
|Good|1|
|Warning|2|
|Bad|3|

---

### ErrorTemplate

<a id="schemaerrortemplate"></a>
<a id="schema_ErrorTemplate"></a>
<a id="tocSerrortemplate"></a>
<a id="tocserrortemplate"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Resolution|string|false|true|None|
|Reason|string|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Resolution": "string",
  "Reason": "string",
  "property1": null,
  "property2": null
}

```

---

### IEqualityComparerOfString

<a id="schemaiequalitycomparerofstring"></a>
<a id="schema_IEqualityComparerOfString"></a>
<a id="tocSiequalitycomparerofstring"></a>
<a id="tocsiequalitycomparerofstring"></a>

```json
{}

```

---

### LastStatusData

<a id="schemalaststatusdata"></a>
<a id="schema_LastStatusData"></a>
<a id="tocSlaststatusdata"></a>
<a id="tocslaststatusdata"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Index|any|false|true|None|
|Status|[StatusEnum](#schemastatusenum)|false|false|None|
|Value|any|false|true|None|
|DisplayName|string|false|true|None|
|AssetId|string|false|true|None|
|DataRetrievalTime|date-time|false|false|None|

```json
{
  "Index": null,
  "Status": 0,
  "Value": null,
  "DisplayName": "string",
  "AssetId": "string",
  "DataRetrievalTime": "2019-08-24T14:15:22Z"
}

```

---

### MultiStatusResultOfLastStatusDataAndChildErrorTemplate

<a id="schemamultistatusresultoflaststatusdataandchilderrortemplate"></a>
<a id="schema_MultiStatusResultOfLastStatusDataAndChildErrorTemplate"></a>
<a id="tocSmultistatusresultoflaststatusdataandchilderrortemplate"></a>
<a id="tocsmultistatusresultoflaststatusdataandchilderrortemplate"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Reason|string|false|true|None|
|Error|string|false|true|None|
|OperationId|string|false|true|None|
|Data|[[LastStatusData](#schemalaststatusdata)]|false|true|None|
|ChildErrors|[[ChildErrorTemplate](#schemachilderrortemplate)]|false|true|None|

```json
{
  "Reason": "string",
  "Error": "string",
  "OperationId": "string",
  "Data": [
    {
      "Index": null,
      "Status": 0,
      "Value": null,
      "DisplayName": "string",
      "AssetId": "string",
      "DataRetrievalTime": "2019-08-24T14:15:22Z"
    }
  ],
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Resolution": "string",
      "Reason": "string",
      "StatusCode": 0,
      "property1": null,
      "property2": null
    }
  ]
}

```

---

### ChildErrorTemplate

<a id="schemachilderrortemplate"></a>
<a id="schema_ChildErrorTemplate"></a>
<a id="tocSchilderrortemplate"></a>
<a id="tocschilderrortemplate"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Resolution|string|false|true|None|
|Reason|string|false|true|None|
|StatusCode|int32|false|false|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Resolution": "string",
  "Reason": "string",
  "StatusCode": 0,
  "property1": null,
  "property2": null
}

```

---
