## Account API
API for retrieving and updating user details

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>api_key</strong></td>
    <td><em>string</em></td>
    <td>Unique identifier used for logging into the dawn API</td>
    <td><code>"abfc287239862398"</code></td>
  </tr>
  <tr>
    <td><strong>created_at</strong></td>
    <td><em>date-time</em></td>
    <td>when account was created</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>email</strong></td>
    <td><em>email</em></td>
    <td>User email</td>
    <td><code>"wearethatguy@gmail.com"</code></td>
  </tr>
  <tr>
    <td><strong>id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of account</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>updated_at</strong></td>
    <td><em>date-time</em></td>
    <td>when account was updated</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>username</strong></td>
    <td><em>string</em></td>
    <td>A String used for identifying users</td>
    <td><code>"ThatGuy417"</code></td>
  </tr>
</table>

### Account API Info
Info for existing account.

```
GET /account
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/account
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "username": "ThatGuy417",
  "api_key": "abfc287239862398",
  "email": "wearethatguy@gmail.com"
}
```

### Account API Update
Update an existing account.

```
PATCH /account
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>password</strong></td>
    <td><em>string</em></td>
    <td>A password.</td>
    <td><code>"45fancypants"</code></td>
  </tr>
  <tr>
    <td><strong>username</strong></td>
    <td><em>string</em></td>
    <td>A String used for identifying users</td>
    <td><code>"ThatGuy417"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X PATCH https://dawn.dev/account
-H "Content-Type: application/json" \
-d '{"username":"ThatGuy417","password":"45fancypants"}'
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "username": "ThatGuy417",
  "api_key": "abfc287239862398",
  "email": "wearethatguy@gmail.com"
}
```


## Account SSH-Keys
API for managing user SSH-keys

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>created_at</strong></td>
    <td><em>date-time</em></td>
    <td>when key was created</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>fingerprint</strong></td>
    <td><em>string</em></td>
    <td>Fingerprint</td>
    <td><code>"c0:ca:bf:73:c1:da:2e:23:48:82:55:98:17:33:1c:06"</code></td>
  </tr>
  <tr>
    <td><strong>id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of key</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>key</strong></td>
    <td><em>string</em></td>
    <td>Key</td>
    <td><code>"..."</code></td>
  </tr>
  <tr>
    <td><strong>updated_at</strong></td>
    <td><em>date-time</em></td>
    <td>when key was updated</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
</table>

### Account SSH-Keys Create
Create a new key.

```
POST /account/keys
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>key</strong></td>
    <td><em>string</em></td>
    <td></td>
    <td></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/account/keys
-H "Content-Type: application/json" \
-d '{"key":null}'
```


#### Response Example
```
HTTP/1.1 201 Created
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "key": "...",
  "fingerprint": "c0:ca:bf:73:c1:da:2e:23:48:82:55:98:17:33:1c:06"
}
```

### Account SSH-Keys Delete
Delete an existing key.

```
DELETE /account/keys/{key_id}
```


#### Curl Example
```term
$ curl -n -X DELETE https://dawn.dev/account/keys/$KEY_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "key": "...",
  "fingerprint": "c0:ca:bf:73:c1:da:2e:23:48:82:55:98:17:33:1c:06"
}
```

### Account SSH-Keys Info
Info for existing key.

```
GET /account/keys/{key_id}
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/account/keys/$KEY_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "key": "...",
  "fingerprint": "c0:ca:bf:73:c1:da:2e:23:48:82:55:98:17:33:1c:06"
}
```

### Account SSH-Keys List
List existing keys.

```
GET /account/keys
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/account/keys
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
[
  {
    "created_at": "2012-01-01T12:00:00Z",
    "id": "01234567-89ab-cdef-0123-456789abcdef",
    "updated_at": "2012-01-01T12:00:00Z",
    "key": "...",
    "fingerprint": "c0:ca:bf:73:c1:da:2e:23:48:82:55:98:17:33:1c:06"
  }
]
```


## App API
API for managing user apps

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>created_at</strong></td>
    <td><em>date-time</em></td>
    <td>when app was created</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>env</strong></td>
    <td><em>object</em></td>
    <td>ENV variables</td>
    <td><code>["HYBRID","true"]</code></td>
  </tr>
  <tr>
    <td><strong>formation</strong></td>
    <td><em>object</em></td>
    <td></td>
    <td><code>["web",1]</code></td>
  </tr>
  <tr>
    <td><strong>git</strong></td>
    <td><em>string</em></td>
    <td>repo name for app</td>
    <td><code>"grave-pare-24"</code></td>
  </tr>
  <tr>
    <td><strong>id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of app</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>name</strong></td>
    <td><em>string</em></td>
    <td>name of the App</td>
    <td><code>"Saucer UFO"</code></td>
  </tr>
  <tr>
    <td><strong>updated_at</strong></td>
    <td><em>date-time</em></td>
    <td>when app was updated</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
</table>

### App API Create
Create a new app.

```
POST /apps
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>name</strong></td>
    <td><em>string</em></td>
    <td>name of the App</td>
    <td><code>"Saucer UFO"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps
-H "Content-Type: application/json" \
-d '{"name":"Saucer UFO"}'
```


#### Response Example
```
HTTP/1.1 201 Created
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Delete
Delete an existing app.

```
DELETE /apps/{app_id}
```


#### Curl Example
```term
$ curl -n -X DELETE https://dawn.dev/apps/$APP_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Info
Info for existing app.

```
GET /apps/{app_id}
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API List
List existing apps.

```
GET /apps
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
[
  {
    "created_at": "2012-01-01T12:00:00Z",
    "id": "01234567-89ab-cdef-0123-456789abcdef",
    "updated_at": "2012-01-01T12:00:00Z",
    "name": "Saucer UFO",
    "git": "grave-pare-24",
    "formation": {
      "web": 1
    },
    "env": {
      "HYBRID": "true"
    }
  }
]
```

### App API Update
Update an existing app.

```
PATCH /apps/{app_id}
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>name</strong></td>
    <td><em>string</em></td>
    <td>name of the App</td>
    <td><code>"Saucer UFO"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X PATCH https://dawn.dev/apps/$APP_ID
-H "Content-Type: application/json" \
-d '{"name":"Saucer UFO"}'
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Create Gear
Create a new gear on app.

```
POST /apps/{app_id}/gears
```


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/gears
```


#### Response Example
```
HTTP/1.1 201 Created
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API List Gears
List existing gears for app.

```
GET /apps/{app_id}/gears
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID/gears
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
[
  {
    "created_at": "2012-01-01T12:00:00Z",
    "id": "01234567-89ab-cdef-0123-456789abcdef",
    "updated_at": "2012-01-01T12:00:00Z",
    "name": "Saucer UFO",
    "git": "grave-pare-24",
    "formation": {
      "web": 1
    },
    "env": {
      "HYBRID": "true"
    }
  }
]
```

### App API Restart Gears
Restart existing gears for app.

```
POST /apps/{app_id}/gears/restart
```


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/gears/restart
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Create Domain
Create a new domain on app.

```
POST /apps/{app_id}/domains
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>url</strong></td>
    <td><em>url</em></td>
    <td>domain url</td>
    <td><code>"catsrus.org"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/domains
-H "Content-Type: application/json" \
-d '{"url":"catsrus.org"}'
```


#### Response Example
```
HTTP/1.1 201 Created
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API List Domains
List existing domains for app.

```
GET /apps/{app_id}/domains
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID/domains
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
[
  {
    "created_at": "2012-01-01T12:00:00Z",
    "id": "01234567-89ab-cdef-0123-456789abcdef",
    "updated_at": "2012-01-01T12:00:00Z",
    "name": "Saucer UFO",
    "git": "grave-pare-24",
    "formation": {
      "web": 1
    },
    "env": {
      "HYBRID": "true"
    }
  }
]
```

### App API Create Drain
Create a new drain on app.

```
POST /apps/{app_id}/drains
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>url</strong></td>
    <td><em>url</em></td>
    <td>domain url</td>
    <td><code>"catsrus.org"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/drains
-H "Content-Type: application/json" \
-d '{"url":"catsrus.org"}'
```


#### Response Example
```
HTTP/1.1 201 Created
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API List Drains
List existing drains for app.

```
GET /apps/{app_id}/drains
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID/drains
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
[
  {
    "created_at": "2012-01-01T12:00:00Z",
    "id": "01234567-89ab-cdef-0123-456789abcdef",
    "updated_at": "2012-01-01T12:00:00Z",
    "name": "Saucer UFO",
    "git": "grave-pare-24",
    "formation": {
      "web": 1
    },
    "env": {
      "HYBRID": "true"
    }
  }
]
```

### App API Formation
List existing formation for app.

```
GET /apps/{app_id}/scale
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID/scale
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Update Formation
Update formation for app.

```
POST /apps/{app_id}/scale
```


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/scale
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Get ENV
Get ENV for app.

```
GET /apps/{app_id}/env
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID/env
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Update ENV
Update ENV for app.

```
POST /apps/{app_id}/env
```


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/env
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Logs
Get logs URL

```
GET /apps/{app_id}/logs
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/apps/$APP_ID/logs
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```

### App API Run Command
Run command in app.

```
POST /apps/{app_id}/run
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>command</strong></td>
    <td><em>string</em></td>
    <td></td>
    <td></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/apps/$APP_ID/run
-H "Content-Type: application/json" \
-d '{"command":null}'
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Saucer UFO",
  "git": "grave-pare-24",
  "formation": {
    "web": 1
  },
  "env": {
    "HYBRID": "true"
  }
}
```


## Domain API
API for managing app domains

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>created_at</strong></td>
    <td><em>date-time</em></td>
    <td>when domain was created</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of domain</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>updated_at</strong></td>
    <td><em>date-time</em></td>
    <td>when domain was updated</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>url</strong></td>
    <td><em>url</em></td>
    <td>domain url</td>
    <td><code>"catsrus.org"</code></td>
  </tr>
</table>

### Domain API Delete
Delete an existing domain.

```
DELETE /domains/{domain_id}
```


#### Curl Example
```term
$ curl -n -X DELETE https://dawn.dev/domains/$DOMAIN_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "url": "catsrus.org"
}
```

### Domain API Info
Info for existing domain.

```
GET /domains/{domain_id}
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/domains/$DOMAIN_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "url": "catsrus.org"
}
```


## Drain API
API for managing app log drains

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>created_at</strong></td>
    <td><em>date-time</em></td>
    <td>when drain was created</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of drain</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>updated_at</strong></td>
    <td><em>date-time</em></td>
    <td>when drain was updated</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>url</strong></td>
    <td><em>url</em></td>
    <td>domain url</td>
    <td><code>"catsrus.org"</code></td>
  </tr>
</table>

### Drain API Delete
Delete an existing drain.

```
DELETE /drains/{drain_id}
```


#### Curl Example
```term
$ curl -n -X DELETE https://dawn.dev/drains/$DRAIN_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "url": "catsrus.org"
}
```

### Drain API Info
Info for existing drain.

```
GET /drains/{drain_id}
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/drains/$DRAIN_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "url": "catsrus.org"
}
```


## Gear API
API for managing app gears

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>created_at</strong></td>
    <td><em>date-time</em></td>
    <td>when gear was created</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of gear</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>name</strong></td>
    <td><em>string</em></td>
    <td>name of the gear.</td>
    <td><code>"Happy Henry"</code></td>
  </tr>
  <tr>
    <td><strong>number</strong></td>
    <td><em>number</em></td>
    <td>gear number</td>
    <td><code>"1"</code></td>
  </tr>
  <tr>
    <td><strong>type</strong></td>
    <td><em>string</em></td>
    <td>gear type</td>
    <td><code>"web"</code></td>
  </tr>
  <tr>
    <td><strong>updated_at</strong></td>
    <td><em>date-time</em></td>
    <td>when gear was updated</td>
    <td><code>"2012-01-01T12:00:00Z"</code></td>
  </tr>
  <tr>
    <td><strong>uptime</strong></td>
    <td><em>number</em></td>
    <td>duration of the gear's run</td>
    <td><code>"11191"</code></td>
  </tr>
</table>

### Gear API Delete
Delete an existing gear.

```
DELETE /gears/{gear_id}
```


#### Curl Example
```term
$ curl -n -X DELETE https://dawn.dev/gears/$GEAR_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Happy Henry",
  "number": "1",
  "type": "web",
  "uptime": "11191"
}
```

### Gear API Info
Info for existing gear.

```
GET /gears/{gear_id}
```


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/gears/$GEAR_ID
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Happy Henry",
  "number": "1",
  "type": "web",
  "uptime": "11191"
}
```

### Gear API Restart
Restart existing gear

```
POST /gears/{gear_id}/restart
```


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/gears/$GEAR_ID/restart
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "created_at": "2012-01-01T12:00:00Z",
  "id": "01234567-89ab-cdef-0123-456789abcdef",
  "updated_at": "2012-01-01T12:00:00Z",
  "name": "Happy Henry",
  "number": "1",
  "type": "web",
  "uptime": "11191"
}
```


## Gitlab Interface
API for gitlab-shell's querying

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
</table>

### Gitlab Interface Info
Determine if project(name: project) is allowed

```
GET /api/git/allowed
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>action</strong></td>
    <td><em>string</em></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><strong>key_id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of key</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
  <tr>
    <td><strong>project</strong></td>
    <td><em>string</em></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><strong>ref</strong></td>
    <td><em>string</em></td>
    <td></td>
    <td></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/api/git/allowed?action=&key_id=01234567-89ab-cdef-0123-456789abcdef&project=&ref=
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
}
```

### Gitlab Interface Find User by SSH-Key
Find a User by their SSH-Key

```
GET /api/git/discover
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>key_id</strong></td>
    <td><em>uuid</em></td>
    <td>unique identifier of key</td>
    <td><code>"01234567-89ab-cdef-0123-456789abcdef"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X GET https://dawn.dev/api/git/discover?key_id=01234567-89ab-cdef-0123-456789abcdef
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
}
```


## Git Stream
Responsible to streaming live to user during a git push

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
</table>

### Git Stream Info
Info for existing stream.

```
POST /api/stream/hook
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>git</strong></td>
    <td><em>string</em></td>
    <td></td>
    <td></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/api/stream/hook
-H "Content-Type: application/json" \
-d '{"git":null}'
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
}
```


## Session API
API for user login/logout

### Attributes
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>api_key</strong></td>
    <td><em>string</em></td>
    <td>Unique identifier used for logging into the dawn API</td>
    <td><code>"abfc287239862398"</code></td>
  </tr>
</table>

### Session API Login
Login to the Dawn API

```
POST /login
```

#### Optional Parameters
<table>
  <tr>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>password</strong></td>
    <td><em>string</em></td>
    <td>A password.</td>
    <td><code>"45fancypants"</code></td>
  </tr>
  <tr>
    <td><strong>username</strong></td>
    <td><em>string</em></td>
    <td>A String used for identifying users</td>
    <td><code>"ThatGuy417"</code></td>
  </tr>
</table>


#### Curl Example
```term
$ curl -n -X POST https://dawn.dev/login
-H "Content-Type: application/json" \
-d '{"username":"ThatGuy417","password":"45fancypants"}'
```


#### Response Example
```
HTTP/1.1 200 OK
```
```json
{
  "api_key": "abfc287239862398"
}
```



