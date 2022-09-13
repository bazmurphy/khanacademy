DOM event typesSummary: DOM events
===================

Adding event listeners
----------------------

To make sure that the browser calls a particular function when an event happens on an element, you must use [`document.addEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget.addEventListener):

```
var buttonEl = document.getElementById("clicker");
var onButtonClick = function() {
    console.log("Oh golly gosh, you clicked me");
};
buttonEl.addEventListener("click", onButtonClick);
```

You can pass many valid strings as the first argument, see the event types article.

If you want information about the event that happened, you can look at the event object that the browser passes to your callback function:

```
var faceEl = document.getElementById("face");
var onFaceClick = function(e) {
    console.log("You clicked " + e.clientX + " , " + e.clientY);
};
faceEl.addEventListener("click", onFaceClick);
```

There are many properties on the event object, you can see [a full list here](https://developer.mozilla.org/en-US/docs/Web/API/Event).

If you are overriding click behavior on a link or submit behavior on a form, you may want to call `event.preventDefault()` to prevent the browser's default behavior.

Removing event listeners
------------------------

If you no longer need a particular event listener, you can remove it using [`removeEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener):

```
var faceEl = document.getElementById("face");
var onFaceClick = function(e) {
    console.log("You clicked " + e.clientX + " , " + e.clientY);
};
faceEl.addEventListener("click", onFaceClick);
// later...
faceEl.removeEventListener("click", onFaceClick);
```

[![](https://cdn.kastatic.org/images/google_classroom_logo_light_square_36.svg)Google Classroom](https://www.khanacademy.org/computing/computer-programming/html-css-js/html-js-dom-events/a/dom-event-types)[](https://www.khanacademy.org/computing/computer-programming/html-css-js/html-js-dom-events/a/dom-event-types)

[Facebook](https://www.khanacademy.org/computing/computer-programming/html-css-js/html-js-dom-events/a/dom-event-types)[](https://www.khanacademy.org/computing/computer-programming/html-css-js/html-js-dom-events/a/dom-event-types)

[Twitter](https://www.khanacademy.org/computing/computer-programming/html-css-js/html-js-dom-events/a/dom-event-types)

[](mailto:?Subject=I%20just%20learned%20about%20DOM%20event%20types&Body=You%20can%20learn%20about%20it%2C%20too.%20Check%20out%20https%3A%2F%2Fwww.khanacademy.org%2Fcomputing%2Fcomputer-programming%2Fhtml-css-js%2Fhtml-js-dom-events%2Fa%2Fdom-event-types)

[Email](mailto:?Subject=I%20just%20learned%20about%20DOM%20event%20types&Body=You%20can%20learn%20about%20it%2C%20too.%20Check%20out%20https%3A%2F%2Fwww.khanacademy.org%2Fcomputing%2Fcomputer-programming%2Fhtml-css-js%2Fhtml-js-dom-events%2Fa%2Fdom-event-types)

The browser triggers many events. A full list is available in [MDN](https://developer.mozilla.org/en-US/docs/Web/Events), but here are some of the most common event types and event names:

-   **mouse events ([`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent))**: mousedown, mouseup, click, dblclick, mousemove, mouseover, mousewheel, mouseout, contextmenu
-   **touch events ([`TouchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent))**: touchstart, touchmove, touchend, touchcancel
-   **keyboard events ([`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent))**: keydown, keypress, keyup
-   **form events**: focus, blur, change, submit
-   **window events**: scroll, resize, hashchange, load, unload

You might be wondering when to use touch events versus mouse events, since they're so similar.

Touch events are only triggered on touch-enabled devices like smartphones and touch-screen laptops. Mouse events like `click` and `mousemove` are triggered on the majority of browsers and devices. However, in most smartphones, the `mouseover` event isn't triggered at all, because they can't detect a finger hovering over the phone. Some smartphones are adding sensors for that though, so more smartphones will detect `mouseover` in the future.

In most cases, you'll want to listen to mouse events instead of touch events, because those are the most universal.