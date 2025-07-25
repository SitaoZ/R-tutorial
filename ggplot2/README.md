# ggplot 
ggplot2 基于图形语法，使用数据，坐标系统和形状映射等概念作图。

data + geom + coordinate system = plot

作图语法：
```r
ggplot(data = DATA) +
<GEOM_FUNCTION>(mapping = aes(<MAPPINGS>), # 必须的
stat = <STAT>, position = <POSITION) +     # 后面都是可选的
<COORDINATE_FUNCTION> +
<FACET_FUNCTION> +
<SCALE_FUNCTION> + 
<THEME_FUNCTION>
```

## Aesthetic
映射，将数据和图形属性关联起来，包括图形的x轴(x)、y轴(y)、颜色(color)、填充(fill)、线条类型(linetype)、大小(size)、形状(shape)。
该功能的实现使用`aes`。

## Geoms
使用geom(几何对象)函数来表示数据点，使用geom的美学属性来表示变量。每个函数返回一个层。
根据不同的geom特征，可以分成：基本图、辅助线、单个连续变量图、单个离散变量图、
两个连续变量图、一个离散变量和一个连续变量图、两个离散变量图等。
### 基本图 GRAPHICAL PRIMITIVES
```r
geom_blank()
geom_curve()
geom_path()
geom_polygon()
geom_rect()
geom_ribbon()
```

### 辅助线
```r
geom_abline #  diagonal 对角线
geom_hline  #  horizontal 水平线
geom_vline  #  vertical 垂直线
```

### 

## scale 标度设置
标度控制如何将数据值转换为视觉属性的细节。
```r
# 坐标控制
labs()
xlab()
ylab()
ggtitle()

# 坐标轴控制
lims()
xlim()
ylim()

# 透明度控制
scale_alpha()
scale_alpha_continuous()
scale_alpha_binned()
scale_alpha_discrete()
scale_alpha_ordinal()

# 颜色盘控制
scale_colour_brewer() # brewer颜色
scale_fill_brewer()

scale_colour_distiller() # distiller颜色
scale_fill_distiller()

scale_colour_fermenter() # fermenter颜色
scale_fill_fermenter()

# 离散型颜色
scale_colour_hue()
scale_fill_hue()

# 连续性颜色
scale_colour_continuous()
scale_fill_continuous()
scale_colour_binned()
scale_fill_binned()


# 手动创建离散型标度
scale_color_manual(values = c('#619CFF','grey','#F8766D')) # 指定颜色
scale_colour_manual() # 颜色
scale_fill_manual()   # 填充
scale_size_manual()   # 大小
scale_shape_manual()  # 形状
scale_linetype_manual() # 线型
scale_linewidth_manual() # 线宽
scale_alpha_manual()     # 透明度
scale_discrete_manual()  # 通用

# 连续型x&y处理
scale_x_continuous()
scale_y_continuous()
scale_x_log10()
scale_y_log10()
scale_x_reverse()
scale_y_reverse()
scale_x_sqrt()
scale_y_sqrt()

```

## labs

`labs()`函数可以用来标注图形的标题（title）、副标题(subtitle)、右下方标注(caption)、左上方标签、坐标轴标题和其他维度的名称。
使用的如下：
```bash
ggplot(gapminder, aes(
    x = gdpPercap,
    y = lifeExp)) +
  geom_point(alpha = 0.4) + 
  labs(
    title = "各国各年度人均GDP与期望寿命的关系",
    subtitle = "1952-2007",
    tag = "散点图",
    caption = "数据来源：gapminder",
    x = "人均GDP(单位：美元)",
    y = "期望寿命"  )
```

## theme 
`theme`主题，使用
```bash

```
## reference
[ggplot2 cheatsheet](https://github.com/rstudio/cheatsheets/blob/main/data-visualization.pdf)
[ggplot tidyverse reference](https://ggplot2.tidyverse.org/reference/index.html)

