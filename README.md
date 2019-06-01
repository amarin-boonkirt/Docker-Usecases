# Docker-Usecases
show use case in real life

# Run single command
## run phantomjs script
create printsource.js 
scripts from https://stackoverflow.com/questions/28209509/get-javascript-rendered-html-source-using-phantomjs
~~~
var system = require('system');
var page   = require('webpage').create();
// system.args[0] is the filename, so system.args[1] is the first real argument
var url    = system.args[1];
// render the page, and run the callback function
page.open(url, function () {
  // page.content is the source
  console.log(page.content);
  // need to call phantom.exit() to prevent from hanging
  phantom.exit();
});

~~~

~~~
docker run -it --rm -v $PWD:/app:z wernight/phantomjs phantomjs /app/printsource.js "http://<yoursite>"
~~~
