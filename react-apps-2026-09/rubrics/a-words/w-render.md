# Rubric: render

### q-define-render

- **type:** free
- **goal:** w-render
- **move:** DEFINE
- **answer:** rendering is a component working out what its part of the page should look like now
  and putting that on the screen. It happens again whenever what it shows changes, such as the
  count going up after a click, so the screen keeps matching what the app is holding.
- **credit:** full credit for saying a component produces what appears on the screen, its own part
  of the page, and that it happens again when what it shows changes. Half credit for "it shows
  something on the screen" with nothing about the component producing its own part, or nothing
  about it happening again. Do not accept "the page loads" or "the browser displays the page",
  which is the page arriving rather than a component producing its part.

### q-render-vs-reload

- **type:** free
- **goal:** w-render
- **move:** DISTINGUISH
- **answer:** a render happens inside the app that is already running: one component works out and
  puts up its own part of the screen, and everything the app is holding stays. A reload throws the
  whole page away, fetches the app again and starts it from the beginning, so what the app was
  holding is gone.
- **credit:** full credit for both sides: a render updates part of the screen with the app still
  running, while a reload starts the whole page over and loses what the app was holding. Half
  credit for one side stated clearly and the other left vague. Do not accept "a render is faster",
  "a render is automatic and a reload is something you do" on its own, or an answer that treats a
  render as a small reload.

### q-click-reloads-page

- **type:** free
- **goal:** w-render
- **move:** CATCH
- **answer:** clicking Count does not reload the page. The app stays running and the component
  renders again, so only its part of the screen is updated. A reload would fetch the page afresh
  and start the app over, and the count would go back to 0 rather than up by one.
- **credit:** full credit for saying the app keeps running and renders part of the screen again,
  rather than the page being fetched again. Full credit for the evidence version on its own: a
  reload would put the count back to 0. Do not accept a different quibble as the error: that the
  browser showed no spinner, that React is fast, or that the count is saved somewhere.
