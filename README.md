# vue_draggable_table_sum

> 支持拖拽辅助线，改变元素大小，元素拖拽功能

### Installation

**npm**

```
npm install
```

**yarn**

```
yarn
```

### Prop Types

| Property | Type          | Default | Description      |
| :------- | :------------ | :------ | :--------------- |
| id       | string/number | -       | 元素唯一值，必填 |

### event 事件

> resize
> 改变元素大小时触发，返回元素的当前坐标 x,y 和宽高 wdth,height
>
> stop
> 元素停止拖拽时触发，返回元素的当前坐标 x,y 和宽高 wdth,height
>
> drag
> 元素拖拽时触发，返回元素的当前坐标 x,y 和宽高 wdth,height
>
> start
> 元素被选中时触发，返回元素的当前坐标 x,y 和宽高 wdth,height
