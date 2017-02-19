# Nodemon issue demonstration
Possibly https://github.com/remy/nodemon/issues/979, extracted from "koa 2" experiment, consist with additional redundancies

## Steps to reproduce
1. Execute `npm install` command
1. Run `npm start` command, which will start `nodemon`
1. Go to `http://localhost:3000/hello/nodemon`, you should see `Hello nodemon` text
1. Go to `src/app.js` file and change on line 31
from
```js
console.log("Started")
```
to
```js
console.log("hello nodemon")
```

## Expected
Outputed text with "hello nodemon" in stdout and server should still be working

## Actual
Text is not outputed to stdout, `http://localhost:3000/hello/nodemon` doesn't respond

## Observed in
node 7; can't start the server in earlier versions since `async/await` syntax is used

