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
str2 = 'world'
str3 = [[
第一行
第二行
]]

-- table
t1 = {}
t2 = {"hello", "world"}
t3 = {key1 = 100, key2 = 300}
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
print(not true) -- echo:false
print(true and false) -- echo:false
print(true or false) -- echo:true
```

## number
```lua
a = 10
b = 3

print(a + b) -- echo:13
print(a - b) -- echo:7
print(a * b) -- echo:30
print(a / b) -- echo:3.3333333333333
print(a ^ b) -- echo:1000.0
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
print("t1个数"..#t1.."个") -- echo:t1个数2个

t2 = {key1 = 100, key2 = 200}
print(t2.key1) -- echo:100
print(t2["key1"]) -- echo:100

-- 插入
t2["key3"] = 300
-- 删除
t2["key1"] = nil
```

# 分支
```lua
if 条件1 then
	分支1
elseif 条件2 then
    分支2
else
	分支3
end
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
+ break
```lua
for i = 1, 10, 2 do
    if i > 5 then
        break
    end
    print(i)
end
--[[
echo:1
echo:3
echo:5
]]
```

+ goto label -> ::label::
```lua
for i = 1, 10, 1 do
    if i % 2 == 1 then
        goto continue
    end
    print(i)
    ::continue::
end
--[[
echo:2
echo:4
echo:6
echo:8
echo:10
]]
```

# 函数
## 定义及初始化
```lua
-- 函数也是变量，可以进行赋值、作为参数传递
[local] function 函数名(参数列表)
	函数体
	[return 参数列表]
end
```

## 可变参数
```lua
function add_all(...)
    local ret = 0;
    for key, value in pairs({...}) do
        ret = ret + value
    end
    return ret
end

print(add_all(10, 20, 30)) -- echo:60
print(add_all(1, 2, 3, 4)) -- echo:10
```

# string
```lua
-- 字符串全部转为大写字母
print(string.upper("Hello")) -- echo:HELLO
-- 字符串全部转为小写字母
print(string.lower("Hello")) -- echo:hello
-- 在字符串中替换
print(string.gsub("aaaa", "a", "z", 3)) -- echo:zzza    3
-- 返回匹配这个子串的起始索引和结束索引，不存在则返回 nil
print(string.find("Hello Lua user", "Lua", 1)) -- echo:7       9
-- 字符串反转
print(string.reverse("Hello")) -- echo:olleH
-- 返回一个类似printf的格式化字符串
print(string.format("the value is:%d",4)) -- echo:the value is:4
-- 将整型数字转成字符并连接
print(string.char(97,98,99,100)) -- echo:abcd
-- 转换字符为整数值(可以指定某个字符，默认第一个字符
print(string.byte("ABCD",4)) -- echo:68
-- 计算字符串长度
print(string.len("abc")) -- echo:3
-- 返回字符串string的n个拷贝
print(string.rep("abcd",2)) -- echo:abcdabcd
-- 字符串截取
print(string.sub("hello", 2, -1)) -- echo:ello
```

# 迭代器
## 默认迭代函数
```lua
-- 遍历array
for k,v in pairs(array) do
end
-- 遍历array，索引为1234，断掉则结束
for k,v in pairs(array) do
end
```

## 自定义迭代函数
```lua
for 变量列表 in 迭代函数, 状态变量, 控制变量 do
	循环体
end
```

```lua
-- 返回1~9的平方
function square(iteratorMaxCount,currentNumber)
   if currentNumber<iteratorMaxCount
   then
      currentNumber = currentNumber+1
   return currentNumber, currentNumber*currentNumber
   end
end

for i,n in square,3,0
do
   print(i,n)
end
```

# table
