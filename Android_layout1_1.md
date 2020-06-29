# 安卓简单布局

## LinearLayout(线性布局)

### 概述

1. 线性布局的布局的方式是内部控件沿着**水平(Horizontal)**或**垂直(Vertical)**方向排列;
2. 不管空间有多长对不会换行, (可以添加ScrollView, HorizontalScrollView添加滚动条);
3. 本控件可以按照权重分配剩余控件, 使用android:layout_weight属性. 垂直就是分配垂直上的控件, 水平分配分配水平上的空间.

### 常用属性

| 编号 | 属性                  | 属性值                                                       | 解释                                                         |
| ---- | --------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | android:gravity       | left: 靠容器左对齐<br />right: 靠容器右对齐<br />center: 在容器中部对齐 | 可选: 默认left,制定内容控件的对齐方式<br />水平沿着垂直方向对齐<br />垂直沿着水平方向对齐 |
| 2    | android:orientation   | horizontal: 水平排布<br />vertical: 垂直排布                 | 必须: 内部控件的排列方向                                     |
| 3    | android:layout_weight | num: 权重                                                    | 按指定方向分配剩余容器内容(水平或垂直)                       |
|      |                       |                                                              |                                                              |

## RelationLayout(相对布局)

### 概述

1. 参照某个参照物进行布局(父容器, 或兄弟容器);
2. 父容器只有一个(RelationLayout容器), 兄弟容器可以有多个(使用id区分);

### 常用属性

<center>相对于父容器</center>

| 编号 | 属性                            | 属性值                        | 解释 |
| ---- | ------------------------------- | ----------------------------- | ---- |
| 1    | android:layout_centerHorizontal | boolean: 是否位于水平居中位置 |      |
| 2    | android:centerVertical          | boolean: 是否位于垂直居中位置 |      |
| 3    | android:centerInparent          | boolean: 位于容器正中间       |      |
| 4    | android:alignParentTop          | boolean; 位于父容器顶端       |      |
| 5    | android:alignParentBottom       | boolean: 是否位于父容器底端   |      |
| 6    | andrid:alignParentLeft          | boolean:  是否对于容器左对齐  |      |
| 7    | android:alignParentRight        | boolean: 是否位于容器的右对齐 |      |

<center>相对于兄弟容器</center>

| 编号 | 属性                       | 属性值  | 解释               |
| ---- | -------------------------- | ------- | ------------------ |
| 1    | android:layout_toRightOf   | 容器id: | 相对兄弟容器右方位 |
| 2    | android:layout_toLeftOf    | 容器id: | 相对兄弟容器左方位 |
| 3    | android:layout_above       | 容器id: | 相对兄弟容器上方位 |
| 4    | android:layout_below       | 容器id: | 相对兄弟容器底方位 |
| 1    | android:layout_alignTop    | 容器id: | 与兄弟控件上边对齐 |
| 2    | android:layout_alignBottom | 容器id: | 与兄弟控件下边对齐 |
| 3    | android:layout_alignLeft   | 容器id: | 与兄弟控件左边对齐 |
| 4    | android:layout_alignRight  | 容器id: | 与兄弟控件右边对齐 |



### 常用属性

## TableLayout(表格布局)

### 概述

1. 使用行与列来管理布局, 行使用\<TableRow\>标签指定, 列在使用列控件数最多的行而出(一个控件代表一列). 直接添加控件代表独占一行;
2. 在表格布局中, 同一列的宽度是固定的, 由最宽的控件决定.
3. 他继承与LinearLayout, 可以使用layout_weight属性设置权重;

### 常用属性

<center>TableLayout(全局属性)</center>

| 编号 | 属性                    | 属性值                                | 解释                        |
| ---- | ----------------------- | ------------------------------------- | --------------------------- |
| 1    | android:collapseColumns | num: 隐藏的单元格, 多个值使用","隔开. | 1. 隐藏列单元格, 编号0开始; |
| 2    | android:shrinkColumns   | num: 收缩指定的列, 多个使用","隔开    | 1. 搜索单元格, 编号0开始;   |
| 3    | android:stretchColumns  | num: 扩展指定列                       | 1. 扩展指定列, 编号0开始;   |

<center>单元格属性</center>

| 编号 | 属性                  | 属性值                    | 解释 |
| ---- | --------------------- | ------------------------- | ---- |
| 1    | android:layout_column | num: 单元格指定开始位置   |      |
| 2    | android:layout_span   | num: 指定单元格跨越的列数 |      |
|      |                       |                           |      |



## GridLayout(网格布局)

1. 网格布局需要版本号14以上(android4.0), 将整个表格划分为rows行, columns列;
2. 每个网格可以防止一个控件, 可以设置控件的摆放方向. 还可以设置控件的跨行与跨列;

### 常用属性

| 编号 | 属性                | 属性值                                                       | 解释 |
| ---- | ------------------- | ------------------------------------------------------------ | ---- |
| 1    | android:orientation | horizontal: 水平(指定columnCount)<br />vertical: 垂直(指定rowCount) |      |
| 2    | android:rowCount    | num: 指定行数(垂直排列有效)                                  |      |
| 3    | android:columnCount | num: 指定列数(水平排列有效)                                  |      |

<center>用于子控件</center>

| 编号 | 属性                      | 属性值           | 解释 |
| ---- | ------------------------- | ---------------- | ---- |
| 1    | android:layout_row        | num:设置开始行号 |      |
| 2    | android:layout_rowSpan    | num:设置跨列行数 |      |
| 3    | android:layout_column     | num:设置开始列号 |      |
| 4    | android:layout_columnSpan | num:设置跨行数   |      |



## FrameLayout(帧布局)

### 概述

1. 在布局管理器中的控件每一个控件都是单独的一层, 相互不会干扰.
2. 默认位置在父容器的左边, 可以使用子容器的android:layout_gravity改变子控件相对父容器位置;

## AbsoluteLayout(可视化布局)