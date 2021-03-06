:man_page: mongoc_collection_keys_to_index_string

mongoc_collection_keys_to_index_string()
========================================

Synopsis
--------

.. code-block:: c

  char *
  mongoc_collection_keys_to_index_string (const bson_t *keys);

Parameters
----------

* ``keys``: A :symbol:`bson_t <bson:bson_t>`.

Description
-----------

This function shall returns the canonical stringification, as used in :symbol:`mongoc_collection_create_index() <mongoc_collection_create_index>` without an explicit name, of a given key specification.

It is a programming error to call this function on a non-standard index, such one other than a straight index with ascending and descending.

Returns
-------

A string that should be freed with :symbol:`bson_free() <bson:bson_free>`.

