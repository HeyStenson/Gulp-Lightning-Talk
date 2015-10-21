# Gulp Lightning Talk

![Sarah Palin with Big Gulp]
(http://33.media.tumblr.com/f05ba5ce2e8faa461eee27f69ae3d0c7/tumblr_mjs1sxOSdM1qzlc1ro1_500.gif)

### Meet Gulp!

[Gulp](http://gulpjs.com/) is a Node-based task manager. 

Sooo... what's a task manager? Task managers are tools that help developers automate tasks such as minification, concatenation, renaming, unit testing, and more. Along with Gulp, the other common task manager you hear about is [Grunt](http://gruntjs.com/). Basically, if it's a task, large or small, that you have to do frequently, a task manager can help! They are especially useful when you're working with large codebases that need to be pushed into production. 

Gulp uses plugins, which are single-purpose tools that you can combine to accomplish the tasks you need to do. Plugins provide methods for you to use, while it's up to you to define the tasks.

### Using Gulp

In order to use Gulp, you need to install it globally first:
```
npm install gulp -g
```

Once you've done that, you can use it in your other projects! To start using Gulp, you need to run:
```
npm install gulp --save-dev
```

The `--save-dev` flag means that Gulp will be added to your `package.json` file as a dependency.

Next, you need to create a configuration file named `gulpfile.js` to define all the plugins your’re using and the tasks you’ll be running. Open it up! First, you need to require Gulp:
```
var gulp = require('gulp');
```

Then you can start writing Gulp tasks. The basic format is:
```javascript
gulp.task('task-name', function () {
  return gulp.src('source-files') // Get source files with gulp.src
    .pipe(aGulpPlugin()) // Sends it through a gulp plugin
    .pipe(gulp.dest('destination')) // Outputs the file in the destination folder
})
```
To run Gulp, go to the command line and type `gulp`. If you only want to run part of your Gulp program, you can type `gulp task-name` (replacing task-name, of course, with the actual name of the task).

You must also create a default task for Gulp. These tasks will run when you run the `gulp` command in the command line. The format for a default task is essentially the same, but you will specify *default* as the task name. For instance:
```
gulp.task('default', ['watch', 'browserSync']);
```
In this case, I'm saying that the default tasks that will run when you type `gulp` into the command line are *watch* and *browserSync*.

### Gulp methods: 
* Task: You must define a task for Gulp to do.
* Watch: Allows you to run any task whenever a file is changed
* Src: Allows you to run a task on a directory. Matches direct file paths or *globs*, which are collections of filetypes (`*.js`, `*.scss`, etc)
* Dest: The destination for piped files. If the folder you specify doesn't exist, it will be created.

### Some cool plugins:
* [BrowserSync](http://www.browsersync.io/docs/gulp/) task allows you to watch certain files and update the view without refreshing when you save. *This one isn't actually a plugin - you just require the module, configure, then start using it!*
* [Uglify](https://www.npmjs.com/package/gulp-uglify/) minifies JavaScript files.
* [Concat](https://www.npmjs.com/package/gulp-concat/) combines/concatenates JavaScript files.
* [Imagemin](https://www.npmjs.com/package/gulp-imagemin/) minifies image files
* [UnCSS](https://www.npmjs.com/package/gulp-uncss/) to remove unused CSS code. 
* [JSHint](https://www.npmjs.com/package/gulp-jshint/) to help you detect errors in your JavaScript.
* Plus [1800+ more](http://gulpjs.com/plugins/)!
 
These can be combined together when it makes sense to do so - for instance, it's smart to run Concatenate first and Uglify second. In order to use a plugin, you must install it. The documentation will tell you what to do, but in most cases, it's going to be something along the lines of:
```
npm install gulp-uglify --save-dev
```

### Have fun using Gulp!
