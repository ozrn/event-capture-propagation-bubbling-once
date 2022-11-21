# JS30 #25: event-capture-propagation-bubbling-once
This is a JS coding practice that aims to explain some concepts like event bubbling, event capturing, event.stopPropagation and as well as once.
### Event bubbling and capturing
Event bubbling and capturing are two ways of event propagation in the HTML DOM API.<br>
The event is first captured and handled by the innermost element and then propagated to outer elements with bubbling while it is first captured by the outermost element and propagated to the inner elements with capturing. Here are the examples of event bubbling and capturing respectively.

``` 
function logText(e) {
      console.log(this.classList.value);
    }
   divs.forEach(div => div.addEventListener("click", logText)
 ```
 ```
  divs.forEach(div => div.addEventListener("click", logText, {
      capture:true 
    }));
 ```  
### Event.stopPropagation()
If we want to prevent further propagation of the current event in the capturing and bubbling phases, stopPropagation method should be used to prevent propagation of the same event from being called.
```
function logText(e) {
      console.log(this.classList.value);
     
      e.stopPropagation();
   }   
```
### Once
If we want an event listener to be fired only once, this can be achieved by passing an object as an argument to the addEventListener method and specifying that the event is only handled once. If we set once to true, the event will only be fired once.
```
divs.forEach(div => div.addEventListener("click", logText, {
      once:true
    }));
```    



