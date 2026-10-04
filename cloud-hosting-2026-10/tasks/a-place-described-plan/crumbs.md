Crumbs is a recipe-sharing app shaped like your Problem Set 2 app. Here you place only its
frontend and its backend:

- **The frontend:** a React app made with Vite. Before it goes anywhere it is built (`npm run
  build`), which turns it into a folder of plain files, `dist/`: one HTML page, some JavaScript and
  some CSS. The visitor's browser fetches those files and runs them.
- **The backend:** an Express server. It has to be running all the time, listening for requests,
  so that it can answer the frontend's requests for recipes and save new ones.

Crumbs also has a database. Where it is kept belongs to the database-hosting topic, so the plans
below leave it out.

The vendors are made up, so nothing here goes out of date. Each says what it offers, and that is
all you know about it.

- **Brightpage:** hosts a folder of files and sends them, as they are, to anyone who asks. Runs no
  code of yours.
- **Kettle:** runs one program of yours (such as a Node server) all the time.
- **Spark:** hosts a folder of files the way Brightpage does, and also runs short functions: each
  request starts a fresh copy of a function, which answers and stops. It never keeps a program
  running between requests.
- **Harbor:** offers two things under one account: static sites (like Brightpage) and web
  services (like Kettle).

For the plan below, say which part each vendor hosts. Then name every gap (a part with no host)
and every mismatch (a part on a host that cannot run it as the app is now); or say there are none.

### q1

Brightpage for the frontend's built files. Kettle for the Express server.

### q2

Brightpage for the frontend and the backend.

### q3

Kettle runs the Express server, and the server also sends the frontend's built files itself
(`express.static('dist')`).

### q4

Brightpage for the frontend, Spark for the Express server.

### q5

Harbor for both: a static site for the frontend and a web service for the Express server.

### q6

Kettle for the Express server. The frontend doesn't need a host, because it runs in the browser.

### q8

Spark for the frontend's built files, Kettle for the Express server.

### q10

Kettle runs the Express server and sends the built frontend with `express.static('dist')`. I'll
also put the built frontend on Brightpage.

### q11

Brightpage for the frontend's built files. The Express server keeps running on my laptop, where it
runs now.

### q12

Harbor for both: one static site holding the frontend's built files and the Express server's code.

### q13

Spark runs the Express server, and the server also sends the frontend's built files itself
(`express.static('dist')`).
