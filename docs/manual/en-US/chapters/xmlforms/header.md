Header field types reference
----------------------------

### accesslevel

### field

### fieldsearchable

This will display an input box so that you can do a text search to filter your rows.

### fieldselectable

This will display a drop down list with the options you specify.

This element has `<option>` sub-elements defining the available options. Please consult Joomla!'s own element of the same type for more information.

### fieldsql

This will display a custom drop down list where the options are taken from a custom SQL query.

You have to set the following attributes:

* **query** the SQL to execute
* **key_field** the SQL field that should be used as key for the select list
* **value_field** the SQL field that should be used as displayed value for the select list

### filtersearchable

### filterselectable

### filtersql

This is almost the same as **fieldsql** (see above) except that it doesn't create an header, just the drop down list.

### language

### ordering

### published

### rowselect
