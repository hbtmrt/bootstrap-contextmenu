The goal is to show dropdown menu by right clicking an element

# Example
###Menu:
Create a menu

    <ul id="menu1" class="context-menu dropdown-menu">
        <li><a href="#">Action 1</a></li>
        <li><a href="#">Another action 1</a></li>
        <li><a href="#">Something else here 1</a></li>
        <li class="divider"></li>
        <li><a href="#">Separated link 1</a></li>
    </ul>
    
Class "dropdown-menu" for better look. Class "context-menu" is needed for js code.
Bind handlers to menu items.

###Target:
Choose an element to be clicked and set "data-context-menu" attribute. The attribute should contains selector for a context menu.
    
    <a data-context-menu="#menu1" href="#">Menu 1</a>

###Initialize
Use selector for the target:

    $('a').contextmenu()
    
###Use
A "e" data value of a context menu DOM element contains an event object of the right click event. 
Sample handler:
    
    $('#menu1 a').click(function(){
        var $m = $(this).closest('.context-menu');	  
        alert($(
            $m
                .data('e')  // retrieve the event object
                .target     // target DOM Element
            ).text())
    });

