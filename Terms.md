# CRRUuX
## CRUD explained
Most explanations of the REST API are simplified, and follows the CRUD as below
| Code | HTTP Method | Description | * |
|------|------|-------------|---|
| C | POST   | Create |
| R | GET    | Read   |
| U | PUT    | Update | PUT in which is abused to mimick PATCH |
| D | DELETE | Delete |

While what you would really like to do is as follows
| Code | HTTP Method | Description |
|------|------|-------------|
| C  | POST   | Create  |
| R  | GET    | Read    |
| U  | PATCH  | Update  |
| R  | PUT    | Replace |
| Ux | PATCH  | Update mark for deletion  |

Examples below
| Code | HTTP Method | Description |
|------|------|-------------|---|
| C | POST | Create | * |
```JSON
{
  "uuid": "UUID()"
  "field0": "data0"
  "field1": "data1"
  "field2": "data2"
  "field3": "data3"
  "field4": "data4"
}
```
| Code | HTTP Method | Description |
|------|------|-------------|---|
| R  | GET    | Read    | * |
```JSON
{
  "uuid": "UUID()"
}
```
| Code | HTTP Method | Description |
|------|------|-------------|---|
| U  | PATCH  | Update  | * |
```JSON
{
  "uuid": "UUID()"
  "field3": "data"
}
```
| Code | HTTP Method | Description |
|------|------|-------------|---|
| R  | PUT    | Replace | Note Unlike PATCH this backend should overwrite the fields not mentioned. |
```JSON
{
  "uuid": "UUID()"
  "field4": "data"
}
```
| Code | HTTP Method | Description |
|------|------|-------------|---|
| Ux | PATCH  | Update mark for deletion  |
```JSON
{
  "uuid": "UUID()"
  "xDelete": "Date()"
}
```
