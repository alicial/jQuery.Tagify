jQuery Tagify
=============
Author: Alicia Liu

This jQuery plug-in provides a stylized input field for creating tags. It uses the jQuery UI widget.

Demo
----
[http://projects.alicialiu.net/jquery-tagify-demo/](http://projects.alicialiu.net/jquery-tagify-demo/)

Features
--------
* _New!_ Supports full integration with jQuery UI Autocomplete plug-in. Try typing some programming languages into the demo.
* _New!_ Supports blur action. After blur create a tag
* Configurable keys to create a tag
* Backspace on empty field deletes last tag
* Public methods to add and remove tags programatically
* Serialize method is separate, you can call it anytime to get the values from the tag field
* Uses jQuery UI widget, to support callbacks

Pre-reqs
--------
To use this Plugin, you will need

* jQuery
* jQuery UI - Tagify is built using jQuery UI Widget

License
-------
This code is licensed under the MIT Licence: [http://www.opensource.org/licenses/mit-license.php](http://www.opensource.org/licenses/mit-license.php)


Basic Usage
-----------
To use it, simply call it on any input field:

    $('textarea.tagme').tagify();

To read the values in the field, call serialize method, which both returns the tags as a delimited string and enters it into the element that tagify was called on.

    $('textarea.tagme').tagify('serialize');

You can do this on form submit, like this:

    $('form').submit( function() {
        $('textarea').tagify('serialize');
    }); 

Use with AutoComplete
---------------------
jQuery Tagify plays well with jQuery UI Autocomplete Plugin. Setting the position moves the menu of suggestions to align with the div containing the tags, you may also want to set the width of the menu to match the width of your container div in CSS. Adding the close callback function adds the selected value as a tag.

    var myTextArea = $('textarea').tagify();
 
    myTextArea.tagify('inputField').autocomplete({
        source: [whatever you want],
        position: { of: myTextArea.tagify('containerDiv') },
        close: function(event, ui) { myTextArea.tagify('add'); },
    });

More Options
------------
Available options and their defaults are:

* What user can type to complete a tag in char codes. Default: [enter], [comma]

        $('textarea').( {delimiters: [13, 188]} );

* Delimiter for tags in original input field

        $('textarea').( {outputDelimiter: ','} );

* CSS class to style the tagify div and tags, see tagify-style.css

        $('textarea').( {cssClass: 'tagify-container'} );

* Placeholder text

        $('textarea').( {addTagPrompt: 'add tags'} );
        
* Blur action for creating tags

        $('textarea').( {addTagOnBlur: true} );