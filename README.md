# Web-Performance-Metrics

Collection of raw and UX metrics for web front-end performance measurement

## Loading metrics

### M1 - Initial Paint (Priority: low)
The browser's initial paint event.
Some content above the fold is displayed for the first time, which may be limited to just headings and paragraphs.

### M2 - DOMContentLoaded (Priority: medium)
No elements are being resized, moved or re-aligned anymore (not by static CSS).

### M3 - Layout Settlement (Priority: high)
Content above the fold is changed for the last time.
No elements are being resized, moved or re-aligned anymore (not by any JavaScript handlers, or dynamically injected CSS).
Images may be still loading, but occupy space in their defined slot that will not change anymore.
No adverts or other lazy elements are pushing content.

### M4 - Scroll Settlement (Priority: medium)
The browser has finished scrolling to the last position when a "back" or "refresh" button have been pressed, either because of HTML/CSS reflow or JavaScript scrollTo() calls.

### M5 - Above-the-fold Load (Priority: high)
All content above the fold is fully displayed, including images.

### M6 - Load
The Browser "load" event (Priority: medium)
All static content is fully loaded, including images below the fold.
Lazily loaded images will not have been loaded at this stage.

### M7 - Network Settlement
Browser loading spinner stops. (Priority: low)
All initial HTTP requests have been served.
Network sockets may still be open but there are no pending connections.
Exceptions:
- Long-poll requests and Websockets are allowed to stay open.
- Web analytics tracking requests may still be firing from time to time.
- Video streaming connections may still remain open, or new ones may open.
- Network requests fired from post-load events (e.g.: setTimeout, onclick) do not count here.

##Early Interaction metrics
### M8 - Initial Scroll settlement (Priority: high)
Page can be first scrolled at 60fps (E.G.: no jittering because of reflows and repaints still happening).
Beware that if the user scrolls very slowly, the reported refresh rate may be less than 60fps because less paints are actually required. That is not a performance bottleneck.

## Late Interaction metrics
### M9 - Framerate delay caused by non-passive scroll event listeners (Priority: high)

### M10 - Subsequent Scroll settlement (Priority: high)
Page can be scrolled at 60fps again, after interaction handling is completed.
- E.G.: user clicks a button that loads content which causes layout/paint.
- E.G.: user scrolls the page or resizes the window which causes layout/repaint, AD refresh.
Beware that if the user scrolls very slowly, the reported refresh rate may be less than 60fps because less paints are actually required. That is not a performance bottleneck.

