:man_page: mongoc_bulk_operation_remove_one

mongoc_bulk_operation_remove_one()
==================================

Synopsis
--------

.. code-block:: c

  void
  mongoc_bulk_operation_remove_one (mongoc_bulk_operation_t *bulk,
                                    const bson_t *selector);

Remove a single document as part of a bulk operation. This only queues the operation. To execute it, call :symbol:`mongoc_bulk_operation_execute() <mongoc_bulk_operation_execute>`.

Parameters
----------

* ``bulk``: A :symbol:`mongoc_bulk_operation_t <mongoc_bulk_operation_t>`.
* ``selector``: A :symbol:`bson_t <bson:bson_t>` that selects which document to remove.

See Also
--------

:symbol:`mongoc_bulk_operation_remove_one_with_opts() <mongoc_bulk_operation_remove_one_with_opts>`

:symbol:`mongoc_bulk_operation_remove_many_with_opts() <mongoc_bulk_operation_remove_many_with_opts>`

Errors
------

Errors are propagated via :symbol:`mongoc_bulk_operation_execute() <mongoc_bulk_operation_execute>`.

