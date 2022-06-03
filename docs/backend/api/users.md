# Users

## Queries

| Queries: |
|---|
|type Query { <br />  allBadges: [Badge!]! <br />  allUsers: [User!]!<br />  badgeById(id: String): Badge <br />  feed(orderBy: BadgeOrderByDate, skip: Int, take: Int): [Badge!]! <br />  me: User <br />  userById(id: String): User <br />  } |

**allUsers() => <User\> [ ]**

Get all users from db, only admin users.

| Example: |
|---|
|usuarios = allUsers(); |


**userById( id: <String\> ) => <User\>**

Get user from db by id.

| Example: |
|---|
|user = userById(id); |

**me() => <User\>**

Get my user info from db. It uses the session token to extract id and query the db.

| Example: |
|---|
| myUser = me(); |



## Mutations

| Mutations: |
|---|
|type Mutation { <br /> addBadge(data: BadgeCreateInput!): Badge! <br /> issueBadge(data: BadgeCreateInput!): Badge! <br /> login(email: String!, password: String!): AuthPayload <br /> logout: User <br /> setAdmin(id: String!): User <br /> signup(email: String!, name:   String,  password: String!): AuthPayload <br /> }|

**signup( email: <String\>, password: <String\> ) => <AuthPayload\>**

Create a user record in the db.

| Example: |
|---|
|authPayload = signup(email, password); |

**login( email: <String\>, password: <String\> ) => <AuthPayload\>**

Login.

| Example: |
|---|
| authPayload = login(email, password); |

**logout() => <User.connected>**

Logout.

| Example: |
|---|
| logout(); |

**setAdmin( id: <String\> ) => <User\>**

Set user role to admin.

| Example: |
|---|
| user = setAdmin(id); |
