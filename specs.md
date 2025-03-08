# M4 Specs

## Database Schema

![Database Schema](./schema.svg)

start and end are stored in the associated timezone

## Api Specifications

### Users

<details>

<summary><code>POST /users</code></summary>

#### Description

Create a new user

#### Security

role: Admin

#### Body

> | name     | type   | required |
> | -------- | ------ | -------- |
> | name     | string | ✓        |
> | username | string | ✓        |
> | password | string | ✓        |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 201  |             |
> | 400  |             |
> | 403  |             |

</details>

<details>

<summary><code>PUT /users/{id}</code></summary>

#### Description

Update a user

#### Security

role: Admin\
user: Own user

#### Body

> | name     | type   | required |
> | -------- | ------ | -------- |
> | name     | string |          |
> | username | string |          |
> | password | string |          |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  |             |
> | 400  |             |
> | 403  |             |

</details>

<details>

<summary><code>DELETE /users/{id}</code></summary>

#### Description

Delete a user

#### Security

role: Admin

#### Body

> | name | type | required |
> | ---- | ---- | -------- |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  |             |
> | 403  |             |

</details>

<details>

<summary><code>GET /users</code></summary>

#### Description

Get users

#### Body

> | name | type | required |
> | ---- | ---- | -------- |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  | [User]      |

</details>

<details>

<summary><code>POST /users/{id}/timeframes</code></summary>

#### Description

Create a new timeframe

#### Security

role: Admin\
user: Own user

#### Body

> | name  | type    | required |
> | ----- | ------- | -------- |
> | tz    | text    | ✓        |
> | day   | integer | ✓        |
> | start | time    | ✓        |
> | end   | time    | ✓        |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 201  |             |
> | 400  |             |
> | 403  |             |

</details>

<details>

<summary><code>GET /users/{id}/timeframes</code></summary>

#### Description

Get user timeframes

#### Body

> | name | type | required |
> | ---- | ---- | -------- |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  | [Timeframe] |

</details>

### Auth

<details>

<summary><code>POST /auth/login</code></summary>

#### Description

Login

#### Body

> | name     | type   | required |
> | -------- | ------ | -------- |
> | username | string | ✓        |
> | password | string | ✓        |

#### Responses

> | code | description                                |
> | ---- | ------------------------------------------ |
> | 200  | Returns the session cookie in `SET-COOKIE` |
> | 400  |                                            |

</details>

<details>

<summary><code>POST /auth/logout</code></summary>

#### Description

Logout

#### Body

> | name | type | required |
> | ---- | ---- | -------- |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  |             |
> | 400  |             |

</details>

### Timeframes

<details>

<summary><code>PUT /timeframes/{id}</code></summary>

#### Description

Update a timeframe

#### Security

role: Admin\
user: Own user

#### Body

> | name  | type    | required |
> | ----- | ------- | -------- |
> | tz    | text    |          |
> | day   | integer |          |
> | start | time    |          |
> | end   | time    |          |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  |             |
> | 400  |             |
> | 403  |             |

</details>

<details>

<summary><code>DELETE /timeframes/{id}</code></summary>

#### Description

Delete a timeframe

#### Security

role: Admin\
user: Own user

#### Body

> | name | type | required |
> | ---- | ---- | -------- |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  |             |
> | 403  |             |

</details>

<details>

<summary><code>GET /timeframes</code></summary>

#### Description

Get all timeframes

#### Body

> | name | type | required |
> | ---- | ---- | -------- |

#### Responses

> | code | description |
> | ---- | ----------- |
> | 200  | [Timeframe] |

</details>

## Notes
