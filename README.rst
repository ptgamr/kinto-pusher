===============================
Kinto Pusher
===============================

.. image:: https://img.shields.io/travis/Kinto/kinto-pusher.svg
        :target: https://travis-ci.org/Kinto/kinto-pusher

.. image:: https://img.shields.io/pypi/v/kinto-pusher.svg
        :target: https://pypi.python.org/pypi/kinto-pusher

Plug `Kinto notifications <http://kinto.readthedocs.io/en/latest/core/reference/notifications.html>`_
into `Pusher.com <http://pusher.com>`_.

* `Online demo <https://kinto.github.io/kinto-pusher/>`_


Install
-------

::

    pip install kinto-pusher

Depending on your environment, it might be necessary to install the `ffi system library <https://sourceware.org/libffi/>`_ with ``sudo apt-get install libffi-dev``.


Setup
-----

In the Kinto-based application settings:

.. code-block:: ini

    kinto.includes = kinto_pusher

    pusher.app_id = <pusher-app-id>
    pusher.key = <pusher-key>
    pusher.secret = <pusher-secret>

    kinto.event_listeners = pusher
    kinto.event_listeners.pusher.use = kinto_pusher.listener

    # Optional customization
    # kinto.event_listeners.pusher.channel = {bucket_id}-{collection_id}-{resource_name}
    # kinto.event_listeners.pusher.for_actions = create update delete
    # kinto.event_listeners.pusher.for_resources = bucket collection group record


TODO
----

- Add view for authenticated channels
