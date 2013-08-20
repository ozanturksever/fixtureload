Simple Fixture Loader
=====================

Source Directory:
```
_ fixtures
  \_ restapi.json
```

Fixture JSON Structure:
```json
{
    "users": {
        "samples": {
            "a user": {"username": "ozan", "password": "test"},
            "user list": [{"username": "ozan", "password": "gizli0"}, {"username": "okan", "password": "gizli2"}]
        }
    }
}
```

Example:

```python
import fixtureload
fixtureload.set_source_dir('/fixtures') # defaults to .

user_list = fixtureload.load('restapi/users/user list')
# user_list = [{'username': 'ozan', 'password': 'gizli0'}, {'username': 'okan', 'password': 'gizli2'}]

a_user = fixtureload.load('restapi/users/a user')
# a_user = {'username': 'ozan', 'password': 'gizli0'}

```

