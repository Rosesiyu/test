```excel
Name	Grade
A	80
B	90
C	100
```
```python
import xlrd
import xlwt
from xlutils.copy import copy
#读取excel数据
workFile = xlrd.open_workbook("Grades.xls")   #打开Excel文件读取数据
sheet = workFile.sheet_by_name("Math")  #通过名称获取工作表
rows_num = sheet.nrows  # 读取总行数
cols_num = sheet.ncols  # 读取列列数
row_value = []
col_value = []
for i in range(0, rows_num):
    row = sheet.row_values(i)   #读取整行的值
    row_value.append(row)
print(row_value)
>>>[['Name', 'Grade'], ['A', 80.0], ['B', 90.0], ['C', 100.0]]
for j in range(0, cols_num):
    col = sheet.col_values(j)   #读取整列的值
    col_value.append(col)
print(col_value)
>>>[['Name', 'A', 'B', 'C'], ['Grade', 80.0, 90.0, 100.0]]
print(sheet.cell(2, 1).value)   #获取单元格
>>>90.0
#写入excel数据
#创建新的excel，并写入数据后保存
workbook = xlwt.Workbook(encoding='ascii')  #创建excel
worksheet = workbook.add_sheet('Worksheet')     #创建表
worksheet.write(0, 0, label='test')     #往单元格中写入内容
workbook.save('Test.xls')   #保存
#打开已存在的excel，写入并保存
wb = copy(workFile)     #复制这个已打开的文件
ws = wb.get_sheet("Math")   #读取表
ws.write(0, int(cols_num), 'Level')     #向单元格中写入数据
wb.save('Grades.xls')   #保存数据
```
