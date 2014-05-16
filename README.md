Bootstrap-ContextMenuHandler
============================

A simple context menu handler for Twitter bootstrap.


Usage
------

What you need:
Besides bootstrap and jQuery you only need the main.css and main.js

Define a context menu in the DOM. For example:

    <div id="contextMenu1" class="dropdown clearfix contextMenu">
      <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu" style="display:block;position:static;margin-bottom:5px;">
        <li><a id="firstLink" tabindex="-1" href="javascript:void(0)">First link</a></li>
        <li><a id="secondLink" tabindex="-1" href="javascript:void(0)">Second link</a></li>
        <li class="divider"></li>
        <li><a id="lastLink" tabindex="-1" href="javascript:void(0)">Last link</a></li>
      </ul>
    </div>

The plugin:
------

    /*
    * @contextMenu: Context menu to be used
    * @clickable: Clickable section inside the area which trigger the context menu.
    * @area: Area of interest. Optional. Default body.
    */
    ContextMenuHandler.init(contextMenu, clickable, area);
    
    
Initialization through Javascript
------

This example initializes the context menu defined above. When click occurs on elements with the class "clickable". The clickable must be inside of an element with the id "area".

    ContextMenuHandler.init('#contextMenu1', '.clickable', '#area' );
    
Same as above, but now the clickable element may exist anywhere in the DOM. 

    ContextMenuHandler.init('#contextMenu1', '.clickable' );
    
You may initialize the context menu to multiple clickable targets in a area.

    ContextMenuHandler.init('#contextMenu1', '#clickable_1, #clickable_2', '#area' );
    
You also may add 'data-function' and 'data-args' as attributes to the anchors in the context menu. The 'data-args' is optional to the function. For example:

    <li><a tabindex="-1" data-function="doSomething" data-args="hello" href="javascript:void(0)">Action1</a></li>

Then define the function doSomething() in JavaScript. And initialize the context menu as usual:

    ContextMenuHandler.init('#contextMenu1', '.clickable', '#area' );

It´s also simple to add icons to the context menu, see example in the source.


TODO´s
------
Please, help to make this plugin better. Below is a list of things that may be done.

- Add events when initializing the context menu
