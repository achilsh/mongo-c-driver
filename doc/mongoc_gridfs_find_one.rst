:man_page: mongoc_gridfs_find_one

mongoc_gridfs_find_one()
========================

Deprecated
----------

This function is deprecated, use :symbol:`mongoc_gridfs_find_one_with_opts <mongoc_gridfs_find_one_with_opts>` instead.

Synopsis
--------

.. code-block:: c

  mongoc_gridfs_file_t *
  mongoc_gridfs_find_one (mongoc_gridfs_t *gridfs,
                          const bson_t *query,
                          bson_error_t *error)
     BSON_GNUC_DEPRECATED_FOR (mongoc_gridfs_find_one_with_opts);

Parameters
----------

* ``gridfs``: A :symbol:`mongoc_gridfs_t <mongoc_gridfs_t>`.
* ``query``: A :symbol:`bson_t <bson:bson_t>`.
* ``error``: An optional location for a :symbol:`bson_error_t <errors>` or ``NULL``.

Description
-----------

This function shall execute a query on the underlying gridfs implementation. The first file matching ``query`` will be returned.

Errors
------

Errors are propagated via the ``error`` parameter.

Returns
-------

A newly allocated :symbol:`mongoc_gridfs_file_t <mongoc_gridfs_file_t>` or ``NULL`` if no file could be found. You must free the resulting file with :symbol:`mongoc_gridfs_file_destroy() <mongoc_gridfs_file_destroy>` if non-NULL.

