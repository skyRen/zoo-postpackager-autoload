# zoo-postpackager-autoload
## 描述
 - 将当前页面的所有资源依赖自动注入页面中
 - 基于fis-postpackager-autoload
 - 服务于zoo-kernel

## 优化改造列表
 - 之前老版本的fis-postpackager-autoload没有对模块中的css做特殊的处理，采用的方案是如果这个模块被引用了，那么会给所有的页面默认注入这个模块的css文件（如果有的话）。<br>我们将之优化为只有引入这个模块的页面才注入该模块的css文件。（依然没有兼容异步模式，只要引入，不管同步异步，都会提前注入这个模块的css文件）
 - 修复了动态模块编译时候的warn，如`[NOTIC] can't find async resource ['ace/mode/'+opt.language]`