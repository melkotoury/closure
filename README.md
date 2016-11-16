# closure
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
