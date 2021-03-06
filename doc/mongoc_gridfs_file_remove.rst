:man_page: mongoc_gridfs_file_remove

mongoc_gridfs_file_remove()
===========================

Synopsis
--------

.. code-block:: c

  bool
  mongoc_gridfs_file_remove (mongoc_gridfs_file_t *file, bson_error_t *error);

Parameters
----------

* ``file``: A :symbol:`mongoc_gridfs_file_t <mongoc_gridfs_file_t>`.
* ``error``: An optional location for a :symbol:`bson_error_t <errors>` or ``NULL``.

Description
-----------

Removes ``file`` and its data chunks from the MongoDB server.

Returns
-------

Returns true if successful, otherwise false and error is set.

Errors
------

Errors are propagated via the ``error`` parameter.

