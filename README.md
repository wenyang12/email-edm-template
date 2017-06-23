## 安装依赖 gulp 和 gulp-htmlmin模块
```
    npm install gulp gulp-htmlmin  --save-dev
```

## 配置gulpfile.js

```
    var gulp = require('gulp'),
    htmlmin = require('gulp-htmlmin');

    gulp.task('htmlmin', function () {
    var options = {
        removeComments: true,//清除HTML注释
        collapseWhitespace: true,//压缩HTML
        collapseBooleanAttributes: true,//省略布尔属性的值 <input checked="true"/> ==> <input />
        removeEmptyAttributes: true,//删除所有空格作属性值 <input id="" /> ==> <input />
        removeScriptTypeAttributes: true,//删除<script>的type="text/javascript"
        removeStyleLinkTypeAttributes: true,//删除<style>和<link>的type="text/css"
        minifyJS: true,//压缩页面JS
        minifyCSS: true//压缩页面CSS
    };
    gulp.src('./*.html')
        .pipe(htmlmin(options))
        .pipe(gulp.dest('dist'));
});
```

## 运行

```npm start```

最终会在dist文件夹下生成html压缩的压缩文件