Librato BG
============

[![Build Status](https://travis-ci.org/nyaruka/python-librato-bg.svg?branch=master)](https://travis-ci.org/nyaruka/python-librato-bg)
[![Coverage Status](https://coveralls.io/repos/github/nyaruka/python-librato-bg/badge.svg?branch=master)](https://coveralls.io/github/nyaruka/python-librato-bg)

Enables submitting of Librato events in a background thread. Heavily inspired by segment.io's python library which does 
the same.

Usage
-----

```python
from librato_bg import Client

# initialize with Librato API tokens
client = Client(username, token)

# track as your normally would, params are event, value and source.
# This is non-blocking, submission will take place in other thread
client.gauge('user_clicked', 1, 'prod')

# when exiting, flush to join threads and make sure everything is sent
client.join()
```
