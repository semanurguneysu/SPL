## List of Users,Roles,Capabilities

```spl

| rest /services/authentication/users 
| rename title as User, roles as Role 
| stats count by User Role 
| fields - count 
| appendcols 
    [| rest /services/authorization/roles 
    | table title srchIndexesAllowed 
    | rename title as Role] 
| stats values(Role) as Role values(srchIndexesAllowed) as Indexes by User

```
