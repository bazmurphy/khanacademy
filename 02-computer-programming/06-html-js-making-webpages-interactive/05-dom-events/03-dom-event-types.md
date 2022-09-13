DOM event types
===============

The browser triggers many events. A full list is available in [MDN](https://developer.mozilla.org/en-US/docs/Web/Events), but here are some of the most common event types and event names:

-   **mouse events ([`MouseEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent))**: mousedown, mouseup, click, dblclick, mousemove, mouseover, mousewheel, mouseout, contextmenu
-   **touch events ([`TouchEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent))**: touchstart, touchmove, touchend, touchcancel
-   **keyboard events ([`KeyboardEvent`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent))**: keydown, keypress, keyup
-   **form events**: focus, blur, change, submit
-   **window events**: scroll, resize, hashchange, load, unload

You might be wondering when to use touch events versus mouse events, since they're so similar.

Touch events are only triggered on touch-enabled devices like smartphones and touch-screen laptops. Mouse events like `click` and `mousemove` are triggered on the majority of browsers and devices. However, in most smartphones, the `mouseover` event isn't triggered at all, because they can't detect a finger hovering over the phone. Some smartphones are adding sensors for that though, so more smartphones will detect `mouseover` in the future.

In most cases, you'll want to listen to mouse events instead of touch events, because those are the most universal.