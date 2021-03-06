:man_page: mongoc_database_read_write_command_with_opts

mongoc_database_read_write_command_with_opts()
==============================================

Synopsis
--------

.. code-block:: c

  bool
  mongoc_database_read_write_command_with_opts (
     mongoc_database_t *database,
     const bson_t *command,
     const mongoc_read_prefs_t *read_prefs,
     const bson_t *opts,
     bson_t *reply,
     bson_error_t *error);

Execute a command on the server, applying logic for commands that both read and write, and taking the MongoDB server version into account. To send a raw command to the server without any of this logic, use :symbol:`mongoc_database_command_simple <mongoc_database_command_simple>`.

Use this function for commands that both read and write, such as "mapReduce" with an output collection.

Read concern is applied from ``opts`` or else from ``database``. Collation is applied from ``opts`` (:ref:`see example for  <mongoc_client_read_command_with_opts_example>`). Read concern and collation both require MongoDB 3.2 or later, otherwise an error is returned. Read preferences are applied from ``read_prefs`` or else from ``database``. Write concern is applied from ``opts``, or else from ``database``. The write concern is omitted for MongoDB before 3.2.

To target a specific server, include an integer "serverId" field in ``opts`` with an id obtained first by calling :symbol:`mongoc_client_select_server <mongoc_client_select_server>`, then :symbol:`mongoc_server_description_id <mongoc_server_description_id>` on its return value.

``reply`` is always initialized, and must be freed with :symbol:`bson_destroy() <bson:bson_destroy>`.

Parameters
----------

* ``database``: A :symbol:`mongoc_database_t <mongoc_database_t>`.
* ``command``: A :symbol:`bson_t <bson:bson_t>` containing the command specification.
* ``read_prefs``: An optional :symbol:`mongoc_read_prefs_t <mongoc_read_prefs_t>`.
* ``opts``: A :symbol:`bson_t <bson:bson_t>` containing additional options.
* ``reply``: A location for the resulting document.
* ``error``: An optional location for a :symbol:`bson_error_t <errors>` or ``NULL``.

Errors
------

Errors are propagated via the ``error`` parameter.

Returns
-------

``true`` if successful; otherwise ``false`` and ``error`` is set.

A write concern timeout or write concern error is considered a failure.

Example
-------

See the example code for :symbol:`mongoc_client_read_command_with_opts <mongoc_client_read_command_with_opts>`.

