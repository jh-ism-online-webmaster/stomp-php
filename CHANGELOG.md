Changelog stomp-php
-------------------

2.1.0
-----

2.1.0 based fork
----------------

- fixed travis ci setup
- added more unit tests (removed ssl unti tests, they don't depend on stomp client)
- refactoring extracted Connection, Parser, Protocol, ActiveMq, RabbitMq, ConnectionException, ErrorFrameException, UnexpectedResponseException
- fixed dead loops caused by connection exceptions
- removed the posibillity to auto-reconnect outside the connect process (it's quite intransparent and can lead to much more problems than expected)
- added a read buffer seen at https://github.com/camronlevanger/stomp-php/commit/8bca4a55b5db8493f543c7f2d1db13d42455e19d

2.2.1
-----

- fixed deadloop on connection exception (https://github.com/fin-sn-de/stomp-php/issues/1)

2.2.2
-----
- This is the last version which is compatible to original fork!
- all sync operations will throw an exception if they are left unconfimred (https://github.com/fin-sn-de/stomp-php/issues/2)

2.2.3
-----
- setting a client id will not longer lead to an durable subscription (https://github.com/fin-sn-de/stomp-php/issues/3)
- `subscribe` and `subscribe` now have a new parameter `durable` which is `false` as default

2.2.4
-----
- fixed possible nullpointer on broken connections