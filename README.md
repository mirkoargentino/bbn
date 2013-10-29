bbn
===

A simple PHP framework targeted at Single Page Application.

Check out the [Documentation](http://doc.babna.com).

This library includes:

* a Database class, working with mySQL and SQLite: supports database analysis and plenty of return methods
* a History class allowing to store each change done in the database and revert them
* files, images, and PDF files manipulation classes
* HTML generation classes
* various string classes
* users management classes
* an MVC framework
* various tools

Usage
-----

A quick example:

```php
<?php
$db = new \bbn\db\connection($cfg);

\bbn\tools::hdump($this->db->modelize("my_table_name"));

\bbn\tools::dump(($this->db->get_rows("SELECT * FROM my_table_name WHERE status = ?", $var));

\bbn\tools::hdump(($this->db->select(
  "my_table_name", // table
  ["field1", "field2"], // columns
  ["id" => 25] // WHERE
  ));
));

\bbn\tools::dump(($this->db->rselect_all(
  "my_table_name", // table
  [], // all columns
  [["id", "<", 25], ["name", "LIKE", "tri%"]], // WHERE
  ["date" => DESC, "name"], // ORDER
  50, // LIMIT
  20 // START 
));

\bbn\tools::hdump(($this->db->get_col_array("SELECT id FROM mytable WHERE name LIKE ?", "tri%"));
```