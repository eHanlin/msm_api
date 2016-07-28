msm-api
=============

Use base64 encoder on **memcached server**.

You able to see [https://github.com/eHanlin/memcached-session-manager/tree/1.8.3-base64](https://github.com/eHanlin/memcached-session-manager/tree/1.8.3-base64) project.

And python project with java project uses the same **memcached server** to share session.

## Dependency

* pylibmc
* msm-transcoder

## Install

```bash
sudo python setup.py install
```

## Usage

Load a MemorySessionAPI class.

```py
from msm_api import MemorySessionAPI
```

Create a instance.

```py
mem_session_api = MemorySessionAPI( ["memcache.domain.com"] )
```

Get session data.

```py
session_id = "BE88B3F619A52C6C256E89755C2EB6D7"

print mem_session_api.get_user_data( session_id )

print mem_session_api.get_data( session_id )
```

Update user data.

```py
mem_session_api.get_user_data( session_id )

user_data["test"] = "hello world!"

mem_session_api.update_user_data( session_id, user_data )
```

## MemorySessionAPI Method

### get_data( session_id )
> Get a complete data from memcached server

### get_user_data( session_id )
> Get a user data

### update_user_data( session_id, user_data )
> Update a user data
