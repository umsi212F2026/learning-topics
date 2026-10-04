# Rubric: component

### q-define-component

- **type:** free
- **goal:** w-component
- **move:** DEFINE
- **answer:** a component is one of the pieces a React screen is assembled from: a named piece of
  the app that produces a part of what you see, such as the task list, one task's row, or the Add
  box. A screen is built out of several of them, and the same one can be used in more than one
  place.
- **credit:** full credit for saying it is a piece of the screen, a part of the app that produces
  part of what you see, and that screens are assembled from them. Full credit for "a reusable piece
  of the interface". Half credit for "a file" or "a function" alone, which says how a component is
  written rather than what it produces. Do not accept "a page" or "a screen", which is the whole
  thing a component is a piece of, and do not accept "a feature of the app".

### q-component-vs-page

- **type:** free
- **goal:** w-component
- **move:** DISTINGUISH
- **answer:** a page is the whole of what is on screen at one address; a component is one of the
  pieces that whole is assembled from. One page is built out of several components (a heading, the
  Add box, one row per task), and one component can turn up on more than one page.
- **credit:** full credit for the containment: a page is the whole screen and components are the
  pieces it is assembled from, so a page holds many components. Full credit for the reuse version:
  the same component can appear on several pages. Half credit for "a component is smaller", or for
  "a page has its own address and a component doesn't", with nothing about one being built out of
  the other. Do not accept "a component is the code and a page is what the user sees", and do not
  accept an answer in which each page is one component.

### q-two-screens-two-components

- **type:** free
- **goal:** w-component
- **move:** CATCH
- **answer:** the number of screens says nothing about the number of components. Each screen is
  itself assembled from several components, and one component can be used on both screens, so two
  screens is a claim about what the app shows rather than about how it is built.
- **credit:** full credit for saying one screen is built from several components, so two screens
  does not mean two components. Full credit for the reuse half alone: the same component can appear
  on both screens. Do not accept a different quibble as the error: that the app should have more
  screens, that they would have to open the files to count, or that the agent decides how many
  components there are.
