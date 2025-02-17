# GeoEasy V1.0.0
这是一个为了解决我在地理信息处理过程中各种繁琐、重复的工作而编写的软件，希望也对你有用。

## 主界面
可以将待处理的shp文件加载到列表中，选中对应的文件则会在右侧显示该文件的缩略图，也可以直接打开“工具”下的对应功能进行使用。

## 功能一：按值分类
**1. 功能简述**

    选择shp文件内的指定字段，根据字段的唯一值将shp文件分为一个或者多个shp文件。

**2. 使用说明**
- 点击“浏览”打开待处理的shp文件，或者选择已加载到主窗口列表的shp文件，再打开“按值分类”功能；
- 点击“加载字段”展示出文件的所有字段；
- 选择对应字段，然后点击“加载值”加载出该字段的唯一值；
- 滑选需要分类的值，点击选择处理类型。
  
**3. 效果展示**

  
![1 按值分类](https://github.com/user-attachments/assets/f76fd034-ca14-4273-8c75-898122221d2d)



## 功能二：合并
**1. 功能简述**

    将多个shp文件合并成一个文件。
**2. 使用说明**
- 点击“浏览”多选打开待处理的shp文件；
- 选择输出路径并开始处理。
  
**3. 效果展示**

![2 合并](https://github.com/user-attachments/assets/26faaa09-8e34-4867-8198-afeb6acfe8f9)

## 功能三：多段标注
**1. 功能简述**

    将shp字段内容转为cad标注文件，类似arcgis标注转注记的功能，但是可以实现多分式的标注样式，并且标注的字体均为单行文字。
    
**2. 使用说明**
- 点击“浏览”打开待处理的shp文件，或者选择已加载到主窗口列表的shp文件，再打开“多段标注”功能；
- 在对应的位置填上想要标注的字段，不填写则会不生成
- 估算比例可以自定义设置，这里估算的是分母字段的字体比例，此数值会影响生成的分数线的长度，数值越大生成的分数线越短。这里建议分母为中文时使用0.7，分母和数字使用1.43；
- 标注生成的位置为图形面的正中心。
  
**3. 效果展示**
  
![3 多段标注](https://github.com/user-attachments/assets/af3d7357-5404-4fcb-9881-a2856442f498)

**4. 备注说明**
- 请确保shp文件的编码文件.cpg存在，否则可能无法正确读取，常用的有UTF-8、GBK、GB18030等等；
- 生成的dxf文件建议使用版本为2016以上的cad软件打开。

## 功能四：地类统计
**1. 功能简述**
   
    这里我是用来统计某一个勘测定界图内各个地类的面积，当然你可以用来统计你想统计的字段。

**2. 使用说明**
- 载入待处理的shp文件后更改对应的字段名
- 文本拼接部分{ }内除了 " 4f " 的 " 4 " 可以修改，这里是对字段求和后小数位数的限制，其他均不可修改，{ }外可以根据需求进行修改；
- 可以先预览地类统计结果后进行检查，也可以点击开始处理。
  
**3. 效果展示**

![4 DLTB统计](https://github.com/user-attachments/assets/10c41a34-6d1d-4bb5-99c0-b234bd1a7b30)


## 功能五：字段更新
**1. 功能简述**

    将excel内容直接更新进shp文件内，类似arcgis的 " 连接和关联 " 的功能，但不再需要字段计算器再计算。

**2. 使用说明**
- 加载一个xls或者xlsx，程序会读取表格的第一行作为匹配字段；
- 加载shp文件，程序会读取shp文件的字段作为匹配字段；
- 可以选择是否保存为一个新的文件，不生成新的文件则会覆盖保存；
- 选择excel和shp文件进行匹配的字段，这里暂无法读取到FID字段，所以无法选择FID作为匹配字段；
- 选择待更新字段，然后点击运行即可。

**3. 效果展示**

![5 字段更新](https://github.com/user-attachments/assets/0f79d6b0-1693-4169-a98e-c853917b4f1e)


## 功能六：cad转shp
**1. 功能简述**

    将dxf文件转为shp文件，同时将dxf文件闭合线内的文字存到shp文件对应面的字段内。

**2. 使用说明**
- 第一步应先确认文字在闭合线内，这里只需要文字“对正”属性的位置在闭合线内即可；
- 选择需要处理的dxf文件和存储的位置，“新增字段名称”则是设置将文字存储到哪一个字段，程序会根据这个名称新建一个80长度的字符串类型。
- 可以选择是否对输出的shp文件进行定义投影，目前设置了常用的国家2000坐标系，高斯-克吕格投影3度分带，中央子午线102E-123E（同时有对应的34带-41带）。
- 点击开始处理即可。

**3. 效果展示**

![6 cad2shp](https://github.com/user-attachments/assets/4b58c160-1de5-4406-a500-cdc2470a651d)

## 功能七：勘测定界
**1. 功能简述**

    勘测定界图表制作的相关功能。

**2. 备注说明**

    后续或许会更新


## 功能八：无锐角裁剪
**1. 功能简述**

    使用一个要素裁剪另一个要素，功能类似arcgis叠加分析中的“裁剪”，但是当裁剪后的面某一个角度小于指定的角度时再拐一个角度从而避免锐角的产生。

**2. 备注说明**

    后续或许会更新

## 功能九：文本分割
**1. 功能简述**

    一个简单的正则表达式文本分割，可将编号-名称-面积的文本用逗号分隔开。

**2. 使用说明**

    略

**3. 效果展示**

![9 文本分割](https://github.com/user-attachments/assets/264b6073-2903-4165-abf4-1e6825015b55)


## 功能十：按属性选择
**1. 功能简述**

    一个简单的文字拼接功能，主要为了批量化arcgis的 " 按属性选择 “ 功能。

**2. 使用说明**
- 字段名输入根据此字段的值进行选择的字段名；
- 输入运算符；
- 隔行粘贴属性值；
- 输入连接符；
- 点击转换；
- 复制转换后的结果粘贴到arcgis中的WHERE子句中

**3. 效果展示**

![10 按属性选择](https://github.com/user-attachments/assets/11761d69-ee9c-49c8-b249-4faec6e7d60c)

## 特别说明
因为未做win7的兼容性处理，所以win7下运行可能会出现dll缺失导致无法运行的情况。










