# python中的xlwt模块

## 简介

1. 写入Excle文档
2. 安装：pip3 install xlwt
3. 导入：import xlwt

## xlrd 模块方法

1. 写入案例

```python
import xlwt
# 创建对象，设置编码
workbook = xlwt.Workbook(encoding='utf-8')

# 新建sheet表
worksheet = workbook.add_sheet(sheet_name, cell_overwrite_ok=True)  

# 在对应行，列写入值
worksheet.write(0,0, label = 'this is test')
# 保存
workbook.save('Excel_test.xls')
```

2. 设置字体属性

```python
font = xlwt.Font()     #  创建一个font对象，用来保存对字体进行的操作
font.name = '微软雅黑'  # 字体设置为'微软雅黑'
font.bold = True        # 字体加粗
font.underline = True   # 字体加下划线
font.italic = True      # 字体倾斜
style = xlwt.XFStyle()  # 创建一个style对象，用来保存excel的样式
style.font = font       # 将字体信息保存到style对象中
worksheet.write(0, 0, '无字体格式')
# 在坐标为1,0的单元格内添加内容'有字体格式'，并带有字体属性
worksheet.write(1, 0, '有字体格式', style)
```

3. 设置背景

```python
# 创建一个pattern对象，用来保存单元格背景的样式
pattern = xlwt.Pattern()   
# 设置单元格的背景图案样式（0x01-0x12共18种样式）
pattern.pattern = 0x01
# 设置单元格的背景颜色
pattern.pattern_fore_colour = xlwt.Style.colour_map['yellow'] 
style = xlwt.XFStyle()
style.pattern = pattern    # 将背景颜色信息保存到styke对象中
# 在坐标为0,0的单元格内添加内容'有背景'，并带有背景颜色
worksheet.write(0, 0, '有背景颜色', style)
```

4. 合并单元格

```python
# 将坐标为纵坐标0,0和横坐标0,1的两列合并，并添加内容'合并两列'
worksheet.write_merge(0, 0, 0, 1, '合并两列')

# 将纵坐标为1,0和横坐标2,0的两行合并，并添加内容'合并两行'
worksheet.write_merge(1, 2, 0, 0, '合并两行')

# 将纵坐标为3-5横坐标为0-2的三行三列合并，并添加内容'合并三行三列'
worksheet.write_merge(3, 5, 0, 2, '合并三行三列')
```

5. 其他方法

```python
# 设置单元格宽度
worksheet.col(0).width = 200
```
