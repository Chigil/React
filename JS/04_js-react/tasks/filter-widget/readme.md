# Filter Widget

## Short Description

Create a widget for data filtering

![pic1.png](./assets/pic1.png)

## Estimation (h)

40

## Topics

1. React
2. Redux
3. Data structures

## Requirements

* Input data for the component is filters, that are built from several tables.

**Table 1**

![table1.png](./assets/table1.png)

**Table 2**

![table2.png](./assets/table2.png)

There may be any count of such tables.

### Contexts dropdown

**Contexts** dropdown is responsible for tables selection, from which filters are formed afterwards. Initial state - no tables selected.

![pic2.png](./assets/pic2.png)

### Dimensions dropdown

**Dimensions** dropdown items are initialized right after table is selected inside **Contexts** dropdown. Each item from **Dimensions** dropdown stands for a column in respective table.

![pic3.png](./assets/pic3.png) ![pic4.png](./assets/pic4.png)

When a column selected, filter list is populated with all unique rows from selected table+column (see example above, **Test Story** table, **Dimension 5** column)

![pic5.png](./assets/pic5.png) ![pic6.png](./assets/pic6.png)

### Search

Implement three types of search:

1. Exact match
1. Partial match
1. Starts with

Alphabetical sorting should be implemented as well.

![pic7.png](./assets/pic7.png)

## Advanced Requirements

-   Drag-n-Drop

![pic8.png](./assets/pic8.png)

-   Persistence

There must be an option to save / restore widget's state.

- Panels page

Create a page that will display 10 panels, each panel contains a button that opens a widget by clicking on it. The panel should also contain an area that is responsible for displaying the current state of the widget.

![panels](./assets/panels.png)

### Tech tips

Widget's state should be kept in reducer (redux).

State getter must return the following data structure:

```javascript
const result = [
    {
        tableId: 1,
        filters: [
            { columnId: 1, name: 'Google' },
            { columnId: 2, name: 'Test' },
            { columnId: 2, name: 'react' },
            { columnId: 3, name: 'css' },
        ],
    },
    {
        tableId: 2,
        filters: [
            { columnId: 1, name: 'Google' },
            { columnId: 2, name: 'Test' },
            { columnId: 2, name: 'react' },
            { columnId: 3, name: 'css' },
        ],
    },
];
```
