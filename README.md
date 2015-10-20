# Gulp-Lightning-Talk
A quick talk about Gulp, a build tool that lets you automate tasks.

Gulp is a Node-based task manager. Sooo... what's a task manager? Task managers are tools that help developers automate tasks such as minification, concatenation, renaming, unit testing, and more. Along with Gulp, the other common task manager you hear about is Grunt. Gulp uses plugins, which are single-purpose tools that you can combine to accomplish the tasks you need to do. 

In order to use Gulp, you need to install it globally first:
`npm install gulp -g`

Once you've done that, you can use it in your other projects! To start using Gulp, you need to run:
`npm install gulp --save-dev`

The `--save-dev` flag means that Gulp will be added to your package.json file as a dependency.

Next, you need to create a configuration file named gulpfile.js to define all the plugins your’re using and the tasks you’ll be running. Open it up! First, you need to require Gulp:
`var gulp = require('gulp');`

Then you can start writing Gulp tasks. The basic format is:
```
gulp.task('task-name', function () {
  return gulp.src('source-files') // Get source files with gulp.src
    .pipe(aGulpPlugin()) // Sends it through a gulp plugin
    .pipe(gulp.dest('destination')) // Outputs the file in the destination folder
})
```

To run Gulp, go to the command line and type `gulp`. If you only want to run part of your Gulp program, you can type `gulp task-name` (replacing task-name, of course, with the actual name of the task).

Gulp has 5 methods: task, run, watch, src, and dest.
* Task:
* Run:
* Watch: Allows you to run any task whenever a file is changed
* Src:
* Dest:

Some cool plugins:
* BrowserSync task allows you to watch certain files and update the view without refreshing when you save.
* Uglify minifies JavaScript files.
* Concat combines/concatenates JavaScript files.
* 
