目录 ->[[../目录|目录]]
# 基础
## 注释
```lua
-- 单行注释

--[[
多行注释
多行注释
]]
```

## 输出
```lua
print("hello world") -- echo:hello world
```

# 变量
## 类型

| 数据类型     | 描述                        |
| :------- | :------------------------ |
| nil      | 表示一个无效值（在条件表达式中相当于false）。 |
| boolean  | false和true。               |
| number   | 表示双精度类型的实浮点数              |
| string   | 字符串由一对双引号或单引号来表示          |
| function | 由 C 或 Lua 编写的函数           |
| userdata | 表示任意存储在变量中的C数据结构          |
| thread   | 表示执行的独立线路，用于执行协同程序        |
| table    | 关联数组，数组的索引可以是数字、字符串或表类型   |

```lua
print(type(nil)) -- echo:nil
print(type(true)) -- echo:boolean
print(type(3.14)) -- echo:number
print(type("hello")) -- echo:string
```

## 定义和初始化
```lua
-- nil
null_arg = nil

-- boolean
bool_arg = true

-- number
num1 = 1
num2 = 3.14
num3 = 0.2e-1

-- string
str1 = "hello"
str2 = [[
第一行
第二行
]]

-- table
t1 = {}
t2 = {"hello", "world"}
t3 = {key1 = 100, key2 = 300}

--function
function func()
end
```

## 作用域
```lua
-- 默认为全局变量
a = 1
-- 加上local为局部变量
local b = 2
```

# 运算
## 赋值运算
```lua
a = 10
a, b = 10, 20
-- 交换
a, b = b, a
```
## nil
```lua
-- 初始化数字变量a，赋值为10
a = 10
-- 销毁a变量
a = nil
```

## boolean
```lua
a = true
print(a) -- echo:true
print(not a) -- echo:false
```

## number
```lua
a = 10
b = 3

print(a + b) -- echo:13
print(a - b) -- echo:7
print(a * b) -- echo:30
print(a / b) -- echo:3.3333333333333
```

## string
```lua
str1 = "2"
str2 = "8"

print(str1 + str2) -- echo:10
print(str1 .. str2) -- echo:28
print(str1 * 3) -- echo: 6

-- 获取字符串长度
print(#"hello你好") -- echo:11
```

## tabel
```lua
t1 = {"first", "second"}
print(t1[1]) -- echo:first

t2 = {key1 = 100, key2 = 200}
print(t2.key1) -- echo:100
print(t2["key1"]) -- echo:100

-- 插入
t2["key3"] = 300
-- 删除
t2["key1"] = nil
```

## function

```lua
function func(n)
	return n + 1
end

print(type(func)) -- echo:function
print(func(3)) -- echo:4

func2 = func
print(func2(5)) -- echo:6
```

# 循环
## while
```lua
while 条件 do
	循环体
end
```

## for
```lua
for 变量=初始值,结束值,步长 do
	循环体
end

for key,value in pairs(表名) do
	循环体
end
```

## repat until(do-while)
```lua
repeat
	循环体
until 条件
```

## 循环控制语句
```lua

```
