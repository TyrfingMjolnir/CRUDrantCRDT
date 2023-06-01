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
| Code | HTTP Method | Description | * |
|------|------|-------------|---|
| C  | POST   | Create  |
| R  | GET    | Read    |
| U  | PATCH  | Update  |
| R  | PUT    | Replace |
| Ux | PATCH  | Update mark for deletion  |

Examples below
| C | POST | Create | * |
|------|------|-------------|---|
{
  "uuid": "UUID()"
  "field0": "data0"
  "field1": "data1"
  "field2": "data2"
  "field3": "data3"
  "field4": "data4"
}

| R  | GET    | Read    |
|------|------|-------------|---|
{
  "uuid": "UUID()"
}

| U  | PATCH  | Update  |
|------|------|-------------|---|
{
  "uuid": "UUID()"
  "field3": "data"
}

| R  | PUT    | Replace | Note Unlike PATCH this backend should overwrite the fields not mentioned. 
|------|------|-------------|---|
{
  "uuid": "UUID()"
  "field4": "data"
}

| Ux | PATCH  | Update mark for deletion  |
|------|------|-------------|---|
{
  "uuid": "UUID()"
  "xDelete": "Date()"
}
