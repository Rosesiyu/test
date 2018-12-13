文件路径处理

```os.listdir()```,显示路径下所有文件

```os.getcwd()```获取当前工作路径

```os.chdir()```切换到路径

```os.mkdir()```创建路径

```os.path.exists()```路径或文件是否存在，如果存在返回True

```os.path.isdir()```路径是否存在，存在返回True，文件存在，返回False

```os.path.basename()```取最后一个路径或文件（类似于取字符串最后一个分隔符后面得字符）

```os.path.dirname()```取除了最后一个路径前面得字符

```os.path.split()```将最后一个分隔符得前后分开

```os.path.splittext()```将字符串路径和扩展名分开

```python
work_path = "E:\script\pythonTest"
test_file = "E:\script\pythonTest\\test.py"
print(os.listdir(work_path))
>>>['.idea', 'filter.py', 'map_reduce.py', 'sorted.py', 'test.py']
print(os.getcwd())
>>>F:\Script\PracticePython
print(os.path.exists(work_path))
>>>True
print(os.path.exists(test_file))
>>>True
print(os.path.isdir(work_path))
>>>True
print(os.path.isdir(test_file))
>>>False
print(os.path.basename(work_path))
>>>pythonTest
print(os.path.basename(test_file))
>>>test.py
print(os.path.dirname(work_path))
>>>E:\script
print(os.path.dirname(test_file))
>>>E:\script\pythonTest
print(os.path.split(work_path))
>>>("E:\script","pythonTest")
print(os.path.split(test_file))
>>>("E:\script\pythonTest","test.py")
print(os.path.splitext(work_path))
>>>("E:\script\pythonTest","")
print(os.path.splitext(test_file))
>>>("E:\script\pythonTest\\test",".py")
```
