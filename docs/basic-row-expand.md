---
id: basic-row-expand
title: Expandable Row
sidebar_label: Expandable Row
---

**[Live Demo For Row Expand](../storybook/index.html?selectedKind=Row%20Expand)**   
**[API & Props Definition](./row-expand-props.html)**

-----

## Expand Mode

`react-bootstrap-table2` allow support click to expand or collapse a row. When you enable row expandable functionality, you have to give [`expandRow.renderer`](./row-expand-props.html#expandrowrenderer-function) to tell what kind of context you want to render in the expanding content, for example: 

```js
const expandRow = {
  renderer: row => (
    <div>....</div>
  )
};

// omit...

<BootstrapTable
  keyField='id'
  data={ products }
  columns={ columns }
  expandRow={ expandRow }
/>

```

## Expand Management
Please check [`expandRow.expanded`](./row-expand-props.html#expandrowexpanded-array), it's used for default expanding usually but also can be used as a external expandation control.   

This is an example for [manage on expands](../storybook/index.html?selectedKind=Row%20Expand&selectedStory=Expand%20Management)

## Customization

### Style/Class
`expandRow.renderer` allow you to render everything in the content of expanding row. You can custom the style or class by yourself. However, a expand row is wrapped by a HTML `tr` element(Parent row). Currently, we support following way to custom the class/style on parent row element:

* For the class of parent row: [`expandRow.parentClassName`](./row-expand-props.html#expandrowparentclassname-string-function)
* For the style of parent row: N/A

In addition, the way to custom the class/style on expanding row element:
* For the class of expanding row: [`expandRow.className`](./row-expand-props.html#expandrowclassname-string-function)
* For the style of expanding row: N/A


### Expand Column
`react-bootstrap-table2` default doesn't render a additional indicator column, just like row selection. But if you want it, you can enable it via [`expandRow.showExpandColumn`](./row-expand-props.html#expandrowshowexpandcolumn-bool)

In addition, we allow you to custom the expand columns in following ways:

* For header cell: [`expandRow.expandHeaderColumnRenderer`](row-expand-props.html#expandrowexpandheadercolumnrenderer-function)
* For normal cell: [`expandRow.expandColumnRenderer`](./row-expand-props.html#expandrowexpandcolumnrenderer-function)


You can render expand column at the right side of table via [`expandRow.expandColumnPosition`](./row-expand-props.html#expandrowexpandcolumnposition-string).


## Event Listening

* [`expandRow.onExpand`](./row-expand-props.html#expandrowonexpand-function) allow you to listen a row is expand or collapse. 
* [`expandRow.onExpandAll`](./row-expand-props.html#expandrowonexpandall-function) for listening the expand/collapse all event.