## func Int(name string, value int, usage string) *int

参数列表
- name string   flag名称
- value int 变量默认值
- usage string 提示信息

返回值
- *int 返回一个int类型的flag值的地址

功能说明
- 定义一个带默认值和提示语句的int类型flag，返回对应值的地址

代码示例
    
    package main
    
    import (
    	"flag"
    	"fmt"
    )
    
    var intFlag = flag.Int("int", 100, "help message for int")
    
    func main() {
    	flag.Parse()
    	fmt.Println("intFlag: ", *intFlag)
    }

代码输出
        
    ./testint 
    intFlag:  100
    
    ./testint -int
    flag needs an argument: -int
    Usage of ./testint:
      -int=100: help message for int
      
    ./testint -int=1000
    intFlag:  1000
    
    ./testint -int -10000
    intFlag:  -10000
