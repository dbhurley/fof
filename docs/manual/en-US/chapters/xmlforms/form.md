Form field types reference
--------------------------

### common fields for all types

For all following fields you can set the following attributes:
* **name**
* **type**
* **label**
* **required**

### accesslevel

This will display a select list with existing Joomla! Access Levels.

You can set the following attributes:
* **class** CSS class (default '')

### button

This will display an input button.

You can set the following attributes:
* **class** CSS class (default '')
* **icon** Bootstrap icon to add to the button (default '')
* **onclick**  "onclick" attribute to add to the button (default '')
* **text** button text value

### cachehandler

This will display a select list with available Joomla! cache handlers

You can set the following attributes:

* **class** CSS class (default '')

### calendar

This will display a calendar/date field.

You can set the following attributes:
* **class** CSS class (default '')
* **format** (defaults '%Y-%m-%d')
* **filter** can be one the following:
** SERVER_UTC convert a date to UTC based on the server timezone
** USER_UTC convert a date to UTC based on the server timezone

### captcha

This will display a captcha input.

You can set no attributes.

### checkbox

This will display a single checkbox input.

You can set the following attributes:
* **class** CSS class (default '')
* **value** the input value
* **checked** the default status for input

### components

This will display a select with a list of installed Joomla! components 

You can set the following attributes:
* **class** CSS class (default '')
* **client_ids** comma separated list of applicable client ids (note: 0 = admin, 1 = site)

### editor

This will display an editarea field for content creation and formatted HTML display.

You can set the following attributes:
* **class** CSS class (default '')

### email

This will display a text input which expects a valid e-mail address.

You can set the following attributes:
* **class** CSS class (default '')
* **show_link** if true put a mailto: link around the address (default false)

### groupedlist

### hidden

This will display a hidden input.

You can set no attributes.

### image

This is an alias for the "media" field type.

### imagelist

This will a media selection field showing images from a specified folder.

You can set the following attributes:
* **class** CSS class
* **directory** folder to search the images in 
* **style** inline style
* **width** HTML width attribute
* **height** HTML height attribute
* **align** HTML align attribute
* **rel** HTML rel attribute
* **title** image title
  
### integer

This will display a text input which expects a valid integer value.

You can set the following attributes:
* **class** CSS class (default '')

### language

This will display a select input of all available Joomla! languages

You can set the following attributes:
* **class** CSS class (default '')

### list

This will display a select input of generic options.

You can set the following attributes:
* **class** CSS class (default '')
* **url** URL template for each element (use [ITEM:ID] as a placeholder for the item id) 
* **show_link** if true, adds a link around each item based on the "url" attribute (default false)

### media

This will display a media selection field.

You can set the following attributes:
* **class** CSS class
* **style** inline style
* **width** HTML width attribute
* **height** HTML height attribute
* **align** HTML align attribute
* **rel** HTML rel attribute
* **title** image title

### model

### ordering

This will display an ordering field for your list, both in traditional Joomla! method and with a new ajax drag'n'drop method.

### password

This will display a password input field.

You can set the following attributes:
* **class** CSS class

### plugins

This will display a select input with a list of all installed Joomla! package.

You can set the following attributes:
* **class** CSS class

### published

This will display a status toggle input field (each time you click on it it changes the status).

You can set the following attributes:
* **show_published** if true, the "published" status will be included in the toggle cycle (default true)
* **show_unpublished** if true, the "unpublished" status will be included in the toggle cycle (default true)
* **show_archived** if true, the "archived" status will be included in the toggle cycle (default false)
* **show_trash** if true, the "trash" status will be included in the toggle cycle (default false)
* **show_all** if true, all the available status will be included in the toggle cycle (default false)

### radio

This will display a radio selection input.

You can set the following attributes:
* **class** CSS class

### rules

### selectrow

### sessionhandler

### spacer

This will display a spacer (static element) between form elements.

You can set no attributes.

### sql

This will display a select input based on a custom SQL query

You can set the following attributes:
* **class** CSS class
* **key_field** the table field to use as key
* **value_field** the table field to display as text
* **query** the actual query to run

### tel

This will display a text input which expects a valid telephone value.

You can set the following attributes:
* **class** CSS class (default '')
* **show_link** if true, a "tel:" link will be appended around the field value (default false)
* **empty_replacement** a string to show in place of the field when it's empty

### text

This will display a single line text input.

You can set the following attributes:
* **class** CSS class (default '')
* **url** URL template for each element (use [ITEM:ID] as a placeholder for the item id) 
* **show_link** if true, a "tel:" link will be appended around the field value (default false)
* **empty_replacement** a string to show in place of the field when it's empty

### textarea

This will display a textarea input.

You can set the following attributes:
* **class** CSS class (default '')

### timezone

This will display a select list with all available timezones.

You can set the following attributes:
* **class** CSS class (default '')

### url

This will display a text input which expects a valid URL.

You can set the following attributes:
* **class** CSS class (default '')
* **show_link** if true, an &lt;a&gt; link will be added around the field value (default false)
* **empty_replacement** a string to show in place of the field when it's empty

### user

This will display a select list with all available Joomla! users.

You can set the following attributes:
* **class** CSS class (default '')
* **show_username** if true, show the username (default true)
* **show_email** if true, show the username (default true)
* **show_name** if true, show the full name (default true)
* **show_id** if true, show the id (default true)
* **show_link** if true, add a link around the field value (default false)
* **show_avatar** if true, show the avatar (default false)
* **avatar_size** size of the image in ???
* **avatar_method** if set to "plugin" use FOF plugins, else fall back to Gravatar
