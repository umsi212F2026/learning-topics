# stack trace

Answer in two or three sentences, in your own words, with nothing open in front of you.

### q1

Your agent pastes these lines from your deployed backend's server log:

```
TypeError: Cannot read properties of undefined (reading 'map')
    at listRooms (/app/server/routes/rooms.js:18:27)
    at Layer.handle [as handle_request] (/app/node_modules/express/lib/router/layer.js:95:5)
    at next (/app/node_modules/express/lib/router/route.js:149:13)
```

What is the difference between the error message in those lines and the stack trace?

### q2

A student writes in their team's notes:

"The server log on our host has no stack trace in it for the last hour, so the app is working for
everyone."

What is wrong with that?
