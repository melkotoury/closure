# closure

Make Sure you donwnloaded [Google Closure Compiler](https://developers.google.com/closure/compiler/docs/gettingstarted_app)

For the purpose of this example , extract the downloaded archive and rename to _**compiler.jar**_

You can minify your _*js*_ file by using google _**closure**_ compiler
```shell
java -jar compiler.jar --js app.js --js_output_file app.min.js
```

You can also run it ith advanced optimization by running this command

```shell
java -jar compiler.jar --js app.js --js_output_file app.min.js --compilation_level ADVANCED_OPTIMIZATIONS
```

or you can use optimization level _White space only_
```shell
java -jar compiler.jar --js app.js --js_output_file app.min.js --compilation_level WHITE_SPACE_ONLY
```

sometime we may need to see the warnings even if we made optimization


```shell
java -jar compiler.jar --js app.js --js_output_file app.min.js --compilation_level ADVANCED_OPTIMIZATIONS --warning_level VERBOSE
```

In case of JQuery for example you may encounter an error **_$ is undeclared_**

so you may want to use --externs option for that and before using it you need to go to their [jquery closure library](https://github.com/google/closure-compiler/tree/master/contrib/externs) and download the file and put it in your project and run this command with --externs option

```shell
java -jar compiler.jar --js app.js --js_output_file app.min.js --compilation_level ADVANCED_OPTIMIZATIONS --warning_level VERBOSE --externs jquery.closure.js
```

If you are using console.log in your code you'd definitely have an error , because the default is when the compiler founds a non declared variable it throw the error , so you may use this option to ignore this kind of error
```shell
java -jar compiler.jar --js app.js --js_output_file app.min.js --compilation_level ADVANCED_OPTIMIZATIONS --warning_level VERBOSE --externs jquery.closure.js --jscomp_off=checkVars
```
