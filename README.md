# gulp-accss - a gulp plugin utilizing ACCSSNODE
## ACCSS - a css compressor written in ansi c

# Usage

    var gulp = require('gulp'),
        source = require('vinyl-source-stream'),
        accss = require('gulp-accss')
        rename = require("gulp-rename");

    gulp.task('minifycss', function () {
        return gulp.src('./css/layout.css')
            .pipe(rename(function (path) {
                path.basename += "-min";
            }))
            .pipe(accss())
            .pipe(gulp.dest('./css/'))
            .pipe(notify("saved: <%= file.path %>"));
    } );

# Options
    //default settings
    accss({
        'restructure' : true,
        'preserve-splitted': false,
        'compat' : 'all'
    })

    //maximum compression (ignores ie hacks)
    accss({
        'compat' : 'none'
    })

    //minimum compression
    accss({
      'restructure' : false,
      'preserve-splitted': true
    })

For Documentation of option values see https://github.com/acwtools/accssnode

More info soon!
