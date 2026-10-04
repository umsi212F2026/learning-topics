# Rubric: event handler

### q-define-event-handler

- **type:** free
- **goal:** w-event-handler
- **move:** DEFINE
- **answer:** an event handler is the piece of the app connected to a particular thing happening on
  the page, such as a click on Add or a key pressed in the box, and it is what runs when that
  happens. It is where "what should the app do about this click" lives.
- **credit:** full credit for saying it is what the app runs in response to a click, a keystroke or
  similar, attached to a particular thing on the page. No credit for naming it again: "a handler"
  and "an event listener" are other names for the same thing rather than a definition. Do not
  accept "the button" or "the click itself", which are the thing clicked and the thing that
  happens, and do not accept "the code behind the app".

### q-handler-vs-event

- **type:** free
- **goal:** w-event-handler
- **move:** DISTINGUISH
- **answer:** the event is the thing that happened: you clicked, and the browser reports a click on
  that button. The handler is the app's response, the piece connected to that event which runs when
  it arrives. The event is reported whether or not anything is connected to it; the handler is what
  makes something come of it.
- **credit:** full credit for placing them on opposite sides: the event is what happened, reported
  by the browser, and the handler is what the app runs because of it. Full credit for "the event
  happens either way; the handler is what is listening for it". Half credit for an answer that
  describes the handler correctly and says nothing about what the event is. Do not accept "two
  names for the same thing", and do not accept an answer in which the handler is the button.

### q-click-not-happening

- **type:** free
- **goal:** w-event-handler
- **move:** CATCH
- **answer:** the click event happens either way: the browser reports a click on that button
  whether or not the app does anything with it. What is missing is a handler connected to that
  event, so nothing runs when it arrives. Nothing appearing on screen says nothing about whether
  the click reached the page.
- **credit:** full credit for separating the two: the click event happens regardless, and what is
  absent is the handler, with nothing connected to run. Do not accept a different quibble as the
  error: that they should have told the agent sooner, that they should check the console first, or
  that the button's label is wrong.
