# golang经验
### no class,use struct + method 来替代。

### interface
* interface 不用implements,应该将运行中做的检查。
* interface{} 可代表Object,包括原始类型int等。

### gdb 调试
* 删除调试符号：go build -ldflags “-s -w”
* 关闭内联优化：go build -gcflags “-N -l”
* b main.main：断点设到开始处
* r args :args 指运行参数
* info goroutines：查看 goroutines 信息
* goroutine 1 bt ：查看指定序号的 goroutine 调用堆栈
* info locals :查看局部变量
* c:continue s:step
* whatis i :查看对象类型
* info frame ：堆栈帧信息

### radix tree & trie tree.
* Radix树与Trie树的思想有点类似。甚至能够把Trie树看为一个基为26的Radix树。
（也能够把Radix树看做是Tire树的变异）
* Trie树一般用于字符串到对象的映射。Radix树一般用于长整数到对象的映射。
* github.com/armon/go-radix

### dep ensure -add golang.org/x/sys 报错
 Could not introduce golang.org/x/sys@master, as its subpackage golang.org/x/sys does not contain usable Go code (*build.NoGoError).. (Package is required by (root).)
  
因为sys下面有子包，需要一个个添加。如：dep ensure -add golang.org/x/sys/unix

### cobra Command Generator
	go get github.com/spf13/cobra/cobra
	cobra init github.com/spf13/newApp
	cobra add serve
	cobra add config
	cobra add create -p 'configCmd'
