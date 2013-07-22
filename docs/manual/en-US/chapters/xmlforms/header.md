Header field types reference
----------------------------

# How header fields work

A header field has two distinct functions:

* It is used to render headers in list views which are used to label the columns of the display and optionally allow you to sort the table by a specific field
* It is used to render filtering widgets (drop-down lists and search boxes). In Joomla! 2.5 you can only render filtering widgets *directly below* a header field in a list table and you can only have up to as many filtering widgets as your fields. In Joomla! 3.x and above the filtering widgets are rendered either *above* the header fields (search boxes) or in the left-hand column (drop-down lists). As in Joomla! 3.x and above the filters are detached from the header fields you can have as many filters as you want, even more than the number of fields you are displaying in the filter list.

A leader field can render only a header, only a filter or both. Most of the header field types render both. Those whose name starts with `filter` will only render a filtering widget, but not a header field. As a result these header fields will only work on Joomla! 3.x and later.


# Common fields for all types

For all following fields you can set the following attributes:

* **name** The name of the header field. This has to match the table field name in the model. 

	If you want to create a header for a calculated field or for a column that doesn't correspond to a table field please use a name that doesn't overlap with the name of a column in the table. If you want to list a field many times (e.g. display a row selection checkbox and the record ID at the same time) you will have to use the same `name` in both headers, but use a different `id` attribute.
* **type** The header type. See below for the available field types, as well as the options which can be specified in each one of them.
* **label** The language string which will be used for the label of the header; this is a language string that will be fed to JText::_() for translation.
* **id** The `id` attribute for this header. Skip it to have FOF create one based on the field name.

	If none is provided FOF will automatically create one using the convention component_modelname_fieldname_LABEL where component is the name of your component, modelname is the name of your model (usually equals to the view name) and fieldname is the name of the field. For example, for a component com_foobar, a view named items and a field named baz we get the language string COM_FOOBAR_ITEMS_BAZ_LABEL.
* **tdwidth** The width of this column in the list table. You can use percentile or pixel units, i.e. `tdwidth="10%"` or `tdwidth="120px"`
* **sortable** Set to "true" if you want to be able to sort the table by this field.
* **filterclass** The CSS class for the filtering widget
* **onchange** The Javascript code to be executed when the filtering widget's value is modified


## Additional attributes for search box filtering widgets

The following attributes apply to all header fields rendering a search box filtering widget:

* **searchfieldname** The name of the field that will be searchable. If omitted it will be the same as the `name` attribute.
* **placeholder** The placeholder text when the field is empty. Useful to explain what kind of information this search field is supposed to be searching in.
* **size** The size (in characters) of the search box
* **maxlength** The maximum length in characters which is allowed to be entered in the field
* **buttons** Set to true (or skip) to show Go and Reset buttons next to the text field. Set to "false" to hide those buttons. The user can still press Enter to submit the form.
* **buttonclass** The CSS class of the Go and Reset buttons


## Additional attributes for drop-down list filtering widgets

This element has `<option>` sub-elements defining the available options. Please consult Joomla!'s own `list` field type for more information.

Since FOF 2.1.0 we allow you to use a programmatically generated data source instead of the hard-coded `<option>` tags. This can be used when you need your code to generate options based on some configuration data, data from the database and so on. You do that by supplying the name of a PHP class and a static method on that class which returns the data. The data must be returned in an indexed array where the key is the key of the drop-down list item and the value is the description (translation key or string). You may also use a simple array containing indexed arrays by using the `source_key` and `source_value` attributes.

The following additional attributes apply to all header fields rendering a drop-down list filtering widget.

* **source_file** (optional) The PHP file which provides the class and method. It is given in the pseudo-URL format e.g. `admin://components/com_foobar/helpers/mydata.php` or `site://components/com_foobar/helpers/mydata.php` for a file relative to the administrator or site root directory respectively.
* **source_class** (required) The name of the PHP class to use, e.g. `FoobarHelperMydata`
* **source_method** (required) The static method of the PHP class to use, e.g. `getSomeFoobarData`
* **source_key** (optional) If you are using an array of indexed arrays, this is the key of the indexed array that contains the key of the drop-down option.
* **source_value** (optional) If you are using an array of indexed arrays, this is the key of the indexed array that contains the value (description) of the drop-down option.
* **source_translate** (optional) By default all values are being translated, i.e. fed through JText::_(). If you don't want that, set this attribute to "false".


# Field Types

### accesslevel

Displays a header field with a viewing access level drop-down filtering widget.

There are no additional attributes to set.

### field

Displays a header field, without any filtering widget.

There are no additional attributes to set.

### fielddate

Displays a header field with a date selection search box filtering widget.

The additional attributes you can set are:

* **readonly** Set to true to make the search box read only
* **disabled** Set to true to disable the search box (it displays but you can't click on it)
* **filter** Skip to show the date/time as entered. Set to SERVER_UTC to convert a date to UTC based on the server timezone. Set to USER_UTC to convert a date to UTC based on the user timezone.

### fieldsearchable

Displays a header field with a search box filtering widget.

There are no additional attributes to set.

### fieldselectable

Displays a header field with a drop-down list filtering widget.

There are no additional attributes to set.

### fieldsql

Displays a header field with a drop-down list filtering widget. The source of the filter values comes from an SQL query.

The additional attributes are:

* **key_field** the table field to use as key
* **value_field** the table field to display as text
* **query** the actual SQL query to run

We recommend avoiding this field type as the query is specific to a particular database server technology. Using the `model` or `fieldselectable` type with a programmatic data source is strongly encouraged.

### filtersearchable

This is the same as fieldsearchable but no header is rendered. Only the filtering widget is rendered. This header field type only works on Joomla! 3.x and later.

### filterselectable

This is the same as fieldselectable but no header is rendered. Only the filtering widget is rendered. This header field type only works on Joomla! 3.x and later.

### filtersql

This is the same as fieldsql but no header is rendered. Only the filtering widget is rendered. This header field type only works on Joomla! 3.x and later.

The same warning applies to using this field type.

### language

Displays a header field with a drop-down list containing the languages installed on your site.

The additional attributes are:

* **client** If set to "site" displays a list of installed front-end languages. If set to "administrator" displays a list of installed back-end languages. Default: site.

### model

Similar to the fieldselectable header, but gets the options from a FOFModel descendant.

You can set the following attributes on top of those of the 'fieldselectable' field type's:

* **model** The name of the model to use, e.g. FoobarModelItems
* **key_field** The name of the field in the model's results which is used as the key value of the drop-down
* **value_field** The name of the field in the model's results which is used as the label of the drop-down
* **translate** Should the value field's value be passed through JText::_() before being displayed?
* **apply_access** Should we respect the view access level, if an access field is present in the model
* **none** The placeholder to be shown if the value is not found in the data returned by the model. This placeholder goes through JText, so you can use a language string if you like.

In order to filter the model you can specify `<state>` sub-elements in the format:

	<state key="state_key">value</state>

Where state_key is the key of a state variable and value is its value. For instance, you could have something like:

	<state key="foobar_category_id">123</state>


### ordering

Displays a header field which allows reordering of your data.

On Joomla! 2.5 it displays the name of the field followed by a disk icon which saves the ordering.

On Joomla! 3.x and later it displays an "up and down triangle" icon. When clicked the AJAX-powered reordering handles in the list view become enabled.

There are no additional attributes.

### published

Displays a header field and a drop-down filtering field for Published / Unpublished and related publishing options.

The additional attributes are:

* **show_published** Should we show the Published status in the filter? Default: true
* **show_unpublished** Should we show the Unpublished status in the filter? Default: true
* **show_archived** Should we show the Archived status in the filter? Default: false
* **show_trash** Should we show the Trashed status in the filter? Default: false
* **show_all** Should we show the All status in the filter? Default: false. You actually don't need this as no selection results in all records, irrespective of their publish state, to be displayed.

### rowselect

Displays a checkbox which, when clicked, automatically selects all the row selection checkboxes in the list.

There are no additional attributes.
