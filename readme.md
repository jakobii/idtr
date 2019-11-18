# Intra-District Transfer Requests

An app for managing Intra-district transfers

## App
```
+----------------------------------------------+
|       Intra-District Transfer Requests       | 
+----------------------------------------------+
|                                              |
|                     LOGIN                    |
|   +--------------------------------------+   |
|   |  username: [____________]            |   |
|   |  password: [____________]    [login] |   |
|   +--------------------------------------+   |
|                                              |
|                                              |
+----------------------------------------------+
```





Main Search Page


- links will be clickable.
- requests will be loaded in bactches of 50.
- requests will be ordered newest to oldest starting from the top.
- more requests will be loaded when the user scrolls to the bottom of the page.

```
GET /transfers/search
+----------------------------------------------+
|       Intra-District Transfer Requests       | 
+----------------------------------------------+
| Search [________________________________]    |
|  Approved [x] | Pendding [x] | Denied [x]    |
+----------------------------------------------+ 
|   +--------------------------------------+   | 
|   | ID: 123    FN: abc    LN: dfg        | ^ | 
|   +--------------------------------------+ | | 
|   +--------------------------------------+ | | 
|   | ID: 123    FN: abc    LN: dfg        | | | 
|   +--------------------------------------+ | |  
|   +--------------------------------------+ | | 
|   | ID: 123    FN: abc    LN: dfg        | | | 
|   +--------------------------------------+ v |  
|   +--------------------------------------+   | 
|   | ID: 123    FN: abc    LN: dfg        |   | 
|   +--------------------------------------+   | 
|   +--------------------------------------+   | 
|   | ID: 123    FN: abc    LN: dfg        |   | 
|   +--------------------------------------+   |    
|   +--------------------------------------+   | 
|   | ID: 123    FN: abc    LN: dfg        |   | 
|   +--------------------------------------+   |  
+----------------------------------------------+
```



Edit transfers page
```
GET /transfers/requests/<id>
+-----------------------------------------------+
|       Intra-District Transfer Requests        |
+-----------------------------------------------+
| Pending [x] | Approved [x] | Denied [x]       |
+-----------------------------------------------+
|                                               |
| Requested School  Current School              |
| [ blah       ]    [ blah      ]               |
|                                               |
| ID            FirstName     LastName          |
| [ 123       ] [ dfg       ] [ dfg       ]     |
|                                               |
| Grade         IEP                             |
| [ blah      ] [ blah      ]                   |
|                                               |
+-----------------------------------------------+
|  +----------------------------------------+ ^ |
|  | xx/xx/xxxx xx:xx:xx       [edit] [del] | | |
|  | Blah Blah Blah...                      | | |
|  +----------------------------------------+ | |
|  +----------------------------------------+ | |
|  | xx/xx/xxxx xx:xx:xx       [edit] [del] | | |
|  | Blah Blah Blah...                      | | |
|  +----------------------------------------+ v |
+-----------------------------------------------+
|  [____________________________________] [add] |
+-----------------------------------------------+
```


## API

manage transfer requests

```bash
GET    /api/transfers        # gets multiple requests with query params
GET    /api/transfers/<id>   # gets a transfer request by id
POST   /api/transfers/<id>   # updates a transfer request by id
PUT    /api/transfers/<id>   # adds a new request
DELETE /api/transfers/<id>   # deletes a request
```

Authenticates users

```bash
GET    /api/session        # authenticates users, returns session cookie
DELETE /api/session/<key>  # removes session cookie
```


## Database

```
Settings
- Key
- Value

sessions
- id
- expiraton

Trsansfers
- id
- submission date
- student id
- first name
- last name
- birth date
- requested school
- current school
- grade
- next grade
- siblings
- IEP
```
