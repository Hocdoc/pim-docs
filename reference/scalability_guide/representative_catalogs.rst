Audit with 3 Representative Catalogs
====================================

We've audited the application with 3 different catalogs, data sets are available here https://github.com/akeneo/catalogs/tree/1.4

+------------------------------------+-----------+------------+-------------+
| **Catalog**                        | **Small** | **Medium** | **Large**   |
+------------------------------------+-----------+------------+-------------+
| Products                           | 5000      | 50000      | 2000000     |
+------------------------------------+-----------+------------+-------------+
| Categories                         | 500       | 2000       | 4000        |
+------------------------------------+-----------+------------+-------------+
| Categories / product               | 2         | 2          | 4           |
+------------------------------------+-----------+------------+-------------+
| Attributes                         | 100       | 400        | 1000        |
+------------------------------------+-----------+------------+-------------+
| Attributes Groups                  | 8         | 15         | 20          |
+------------------------------------+-----------+------------+-------------+
| Attributes / Families              | 50        | 100        | 150         |
+------------------------------------+-----------+------------+-------------+
| % filled attributes                | 75%       | 75%        | 75%         |
+------------------------------------+-----------+------------+-------------+
| %localisable attributes            | 10%       | 5%         | 2%          |
+------------------------------------+-----------+------------+-------------+
| %scopable attributes               | 5%        | 2%         | 1%          |
+------------------------------------+-----------+------------+-------------+
| %scopable + localisable attributes | 2%        | 1%         | < 1%        |
+------------------------------------+-----------+------------+-------------+
| Families                           | 20        | 50         | 400         |
+------------------------------------+-----------+------------+-------------+
| Channels                           | 2         | 2          | 4           |
+------------------------------------+-----------+------------+-------------+
| Locales                            | 1         | 4          | 8           |
+------------------------------------+-----------+------------+-------------+

There are the amount of product values generated in each catalog used to realize the audit:

+------------------------------------+-----------+------------+-------------+
| **Catalog**                        | **Small** | **Medium** | **Large**   |
+------------------------------------+-----------+------------+-------------+
| Product values                     | 257.010   | ...        | ...         |
+------------------------------------+-----------+------------+-------------+

.. note::

    Several of our customers use the PIM with far more data on different axes, 10k attributes, 14k categories, etc.
    If your data set challenges these limits, you may be interested by other audits and related improvements in :doc:`/reference/scalability_guide/index`.
    If you don't find relevant information for your targeted data set, don't hesitate to contact us to explain your use case.
    We improve the product scalability from one minor version to another and are always interested by new use cases to cover.

Installation
------------

The application is installed on a server following the recommended architecture :doc:`/reference/technical_information/index`.

Depending on the catalog, we use a different database storage:

 * Small catalog is installed with the MySQL storage.
 * Medium catalog is installed with the MongoDB storage.
 * Large catalog is installed with MongoDB storage.

Then, we install the `fixtures` via the installer before to import the products through the default product csv import.

.. note::

    You want to know more about how we choose the relevant storage :doc:`/reference/scalability_guide/more_than_5M_product_values`.

Audit User Interface
--------------------

We use the application in production mode, with xdebug disabled, and we expect an optimal user experience for each page and action.

Audit Backend Processes
-----------------------

We run backend processes (bulk actions, imports, exports, rules execution, etc) in production mode, with xdebug disabled.

With lot of data, processes may run for a quite long time but does not consume more memory than what we advise in :doc:`/reference/technical_information/index`.

Audits Results
--------------

+----------------+-------------------+--------------------+
|                | Community Edition | Enterprise Edition |
+----------------+-------------------+--------------------+
| Small MySQL    | Ok                | WIP                |
+----------------+-------------------+--------------------+
| Medium MySQL   | WIP               | WIP                |
+----------------+-------------------+--------------------+
| Medium MongoDB | Ok                | WIP                |
+----------------+-------------------+--------------------+
| Large MongoDB  | WIP               | WIP                |
+----------------+-------------------+--------------------+
