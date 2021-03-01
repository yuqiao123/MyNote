# python中的xlrd模块

## 简介

1. 读取Excle文档，支持xls，xlsx格式
2. 安装：pip3 install xlrd
3. 导入：import xlrd

## xlrd 模块方法

1. 读取Excel

```python
file = 'route_info.xls'             
# 读取Excel信息,生成对象                    
read_book = xlrd.open_workbook(file)
```

2. 获取sheet【表】相关方法，返回xlrd.sheet.Sheet()对象

```python
sheet = read_book.sheets()                 # 获取全部sheet列表  
print(sheet)                                               
print(sheet[0])                            # 通过索引顺序获取     
                                                           
sheet = read_book.sheet_by_name("100路")   # 通过名称获取        
print(sheet)                                               
                                                           
sheet = read_book.sheet_by_index(0)   # 通过索引顺获取            
print(sheet)                                               
```

3. 返回book中所有工作表的名字列表 

```python
sheet_names = read_book.sheet_names()
print(sheet_names)                   
```

4. 检查某个sheet是否导入完毕

```python
is_loaded = read_book.sheet_loaded("100路")
print(is_loaded)    # True
```

5. sheet【行】操作

```python
    print(sheet.nrows)  # 获取该sheet中的有效行数

    print(sheet.row_len(0)) # 返回该行的有效单元格长度

    print(sheet.row(0)) # 3.返回由该列中所有的 单元格对象 组成的列表
    print(sheet.row_slice(0)) # 返回由该列中所有的 单元格对象 组成的列表

    # 4.返回由该行中所有单元格的 数据类型 组成的列表
    print(sheet.row_types(0, start_colx=0, end_colx=None))

    # 5.返回由该行中所有单元格的数据组成的列表
    print(sheet.row_values(0, start_colx=0, end_colx=None)) 
```

6. sheet【列】操作

```python
    print(sheet.ncols)  # 获取该sheet中的有效列数

    print(sheet.col(0)) # 3.返回由该列中所有的 单元格对象 组成的列表
    print(sheet.col_slice(0)) # 返回由该列中所有的 单元格对象 组成的列表

    # 4.返回由该列中所有单元格的 数据类型 组成的列表
    print(sheet.col_types(0, start_colx=0, end_colx=None))

    # 5.返回由该列中所有单元格的数据组成的列表
    print(sheet.col_values(0, start_colx=0, end_colx=None)) 
```

7. sheet【单元格】操作

```python
    print(sheet.cell(0, 0))  # 返回单元格对象          
    print(sheet.cell_tpy(0, 0))  # 返回单元格中的数据类型  
    print(sheet.cell_value(0, 0))  # 返回单元格中的数据  
```

