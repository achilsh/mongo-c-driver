:man_page: mongoc_bulk_operation_update_many_with_opts

mongoc_bulk_operation_update_many_with_opts()
=============================================

Synopsis
--------

.. code-block:: c

  bool
  mongoc_bulk_operation_update_many_with_opts (mongoc_bulk_operation_t *bulk,
                                               const bson_t *selector,
                                               const bson_t *document,
                                               const bson_t *opts,
                                               bson_error_t *error); /* OUT */

This function queues an update as part of a bulk operation. This does not execute the operation. To execute the entirety of the bulk operation call :symbol:`mongoc_bulk_operation_execute() <mongoc_bulk_operation_execute>`.

.. warning::

  ``document`` MUST only contain fields whose key starts with ``$``. See the update document specification for more details.

Parameters
----------

* ``bulk``: A :symbol:`mongoc_bulk_operation_t <mongoc_bulk_operation_t>`.
* ``selector``: A :symbol:`bson_t <bson:bson_t>` that selects which documents to remove.
* ``document``: A :symbol:`bson_t <bson:bson_t>` containing the update document.
* ``opts``: A :symbol:`bson_t <bson:bson_t>` containing additional options.
* ``error``: A :symbol:`bson_error_t <bson:bson_error_t>` any errors that may have occurred.

See Also
--------

:symbol:`mongoc_bulk_operation_update_one_with_opts() <mongoc_bulk_operation_update_one_with_opts>`

Errors
------

Operation errors are propagated via :symbol:`mongoc_bulk_operation_execute() <mongoc_bulk_operation_execute>`, while argument validation errors are reported by the ``error`` argument.

Returns
-------

Returns true on success, and false otherwise.

