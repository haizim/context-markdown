# Grid

A grid is used to harmonize negative space in a layout

## Overview

### Introduction

#### Grids
A grid is a structure with a long history used to align negative space in designs.

Using a grid makes content appear to flow more naturally on your page.

```html
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

#### Columns
Grids divide horizontal space into indivisible units called "columns". All columns in a grid must specify their width as proportion of the total available row width.

All grid systems choose an arbitrary column count to allow per row. Semantic's default theme uses **16 columns**.

The example below shows four `four wide` columns will fit in the first row, `16 / 4 = 4`, and three various sized columns in the second row. `2 + 8 + 6 = 16`

The default column count, and other arbitrary features of grids can be changed by adjusting Semantic UI's underlying theming variables.

```html
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="two wide column"></div>
  <div class="eight wide column"></div>
  <div class="six wide column"></div>
</div>
```

#### Rows
Rows are groups of columns which are aligned horizontally.

Rows can either be *explicit*, marked with an additional `row` element, or *implicit*, automatically occurring when no more space is left in a previous row.

After each group of columns vertical spacing is added to separate each group of columns, creating vertical rhythm.

```html
<div class="ui four column grid">
  <div class="row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Gutters
Grid columns are separated by areas of white space referred to as "gutters". Gutters improve legibility by providing, negative space between page elements.

Gutters remain a constant size regardless of the width of the grid, or how many columns are in a row. To increase the size of gutters in a particular grid, you can use a `relaxed grid` variation.

```html
<div class="ui grid">
  <div class="three column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="eight column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
<div class="ui relaxed grid">
  <div class="three column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="eight column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Negative Margins
Since all grid columns include gutters, grids use negative margins to make sure that the first and last columns sit flush with content outside the grid.

In the following example, you can see even though the top row has padding, the `attached button` still sits flush with the edge of the grid.

In some cases, like when a column or row is `colored`, you may want to avoid using negative margins. You can do this by using a `padded grid` variation.

```html
<div class="ui top attached button">Button before grid</div>
<div class="ui grid">
  <div class="sixteen wide column"></div>
  <div class="ten wide column"></div>
  <div class="six wide column"></div>
</div>
<div class="ui grid">
  <div class="sixteen wide column"></div>
</div>
<div class="ui bottom attached button">Button after grid</div>
```

#### Page Grids
Grids are fluid and will automatically flow in size to take the maximum available width.

Containers are elements designed to limit page content to a reasonable maximum width for display based on the size of the user's screen.

Using a `ui grid container` is the best way to include top-level page content inside a grid.

> In version `1.x` of Semantic UI `page grid` were used to contain the maximum width of grids holding page content. Page grid have been deprecated in favor for the simpler `container` element.

### Columns

#### Automatic Flow
Most grids do not need to specify rows. Content will automatically flow to the next row when all the grid columns are taken in the current row.

```html
<div class="ui grid">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

#### Column Content
Since columns use padding to create gutters, content stylings should not be applied directly to columns, but to elements inside of columns.

```html
<div class="ui three column grid">
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Column Widths
Column widths can be specified using `(x) wide` class names. If a column cannot fit in a row it will automatically flow to the next row

```html
<div class="ui grid">
  <div class="eight wide column"></div>
  <div class="eight wide column"></div>
  <div class="ten wide column"></div>
  <div class="six wide column"></div>
  <div class="four wide column"></div>
  <div class="twelve wide column"></div>
  <div class="two wide column"></div>
  <div class="fourteen wide column"></div>
  <div class="sixteen wide column"></div>
</div>
```

### Rows

#### Grouping
Row wrappers allow you to apply variations to a group of columns.

```html
<div class="ui four column grid">
  <div class="two column row">
    <div class="column"></div>
  </div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Clearing Content
Row wrappers will automatically clear previous columns, making them useful when using `floated` variations.

```html
<div class="ui grid">
  <div class="four column row">
    <div class="left floated column"></div>
    <div class="right floated column"></div>
  </div>
  <div class="row">
    <div class="three wide column"></div>
    <div class="eight wide column"></div>
    <div class="five wide column"></div>
  </div>
</div>
```

#### Special Grids
Additionally, some types of grids, like `divided` or `celled` require row wrappers to apply formatting correctly.

```html
<div class="ui internally celled grid">
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/centered-paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

### Varying Grids

#### Nesting Grids
Grids can be placed inside of other grids, letting you sub-divide columns.

```html
<div class="ui two column grid">
  <div class="column">
    <div class="ui three column grid">
      <div class="column"></div>
      <div class="column"></div>
      <div class="column"></div>
    </div>
  </div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column">
    <div class="ui grid">
      <div class="ten wide column"></div>
      <div class="six wide column"></div>
    </div>
  </div>
</div>
```

#### Colored
Grids can use named **colors** variations to add background colors, but only with `padded grid` that do not include negative margins.

To include a color that is not available in the default palette its perfectly fine to use CSS

```html
<div class="ui equal width center aligned padded grid">
  <div class="row">
    <div class="olive column">
      Olive
    </div>
    <div class="black column">
      Black
    </div>
  </div>
  <div class="row" style="background-color: #869D05;color: #FFFFFF;">
    <div class="column">Custom Row</div>
  </div>
  <div class="row">
    <div class="black column">
      Black
    </div>
    <div class="olive column">
      Olive
    </div>
  </div>
</div>
```

#### Automatic Column Count
The `equal width` variation will automatically divide column width evenly. This is useful with dynamic content where you do not know the column count in advance.

```html
<div class="ui equal width grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="equal width row">
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Centering Content
If a row does not take up all sixteen grid columns, you can use a `centered` variation to center the column contents inside the grid.

```html
<div class="ui two column centered grid">
  <div class="column"></div>
  <div class="four column centered row">
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Significant Word Order
Grids include many variations for adjusting things like vertical or horizontal alignment, text alignment, or default gutter sizes.

Some multi-word variations, like `left floated` or `right aligned` are word-order dependent and require you to use adjacent class names.

```html
<div class="ui right aligned grid">
  <div class="left floated right aligned six wide column">
    <div class="ui segment">
      Left floated right aligned column
    </div>
  </div>
  <div class="right floated left aligned six wide column">
    <div class="ui segment">
      Right floated left aligned column
    </div>
  </div>
  <div class="center aligned two column row">
    <div class="column">
      <div class="ui segment">
      Center aligned row
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
      Center aligned row
      </div>
    </div>
  </div>
  <div class="sixteen wide column">
    <div class="ui segment">
      Right Aligned Grid
    </div>
  </div>
</div>
```

### Responsive Grids

#### Containers
A container can be used alongside a grid to provide a responsive, fixed width container for wrapping the contents of a page.

```html
<div class="ui grid container">
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
  <div class="four wide column"></div>
</div>
```

#### Stackable
A `stackable grid` will automatically stack rows to a single columns on mobile devices

```html
<div class="ui stackable four column grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Reverse Order
Semantic includes special `reversed` variations that allow you to reverse the order of columns or rows by device

```html
<div class="ui mobile reversed equal width grid">
  <div class="column">
    First
  </div>
  <div class="column">
    Second
  </div>
  <div class="column">
    Third
  </div>
</div>
```

#### Doubling
A `doubling` grid will double column widths for each device jump.

```html
<div class="ui grid">
  <div class="doubling eight column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="doubling six column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
  <div class="doubling four column row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
  </div>
</div>
```

#### Manual Tweaks
Although design patterns like `doubling` or `stackable` are useful at simplifying responsive styling, you can also manually tweak device presentation by specifying `(x) wide device` or `device only` columns or rows.

```html
<div class="ui centered grid">
  <div class="computer only row">
    <div class="column"></div>
  </div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
  <div class="six wide tablet eight wide computer column"></div>
</div>
```

## Definition

### Types

#### Grid
A basic grid

```html
<div class="ui grid">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

#### Divided
A grid can have dividers between its columns

```html
<div class="ui three column divided grid">
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
  </div>
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
    </div>
  </div>
</div>
```

#### Vertically Divided
A grid can have dividers between rows

```html
<div class="ui vertically divided grid">
  <div class="two column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="three column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```

#### Celled
A grid can have rows divided into cells

```html
<div class="ui celled grid">
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="thirteen wide column">
      <img class="ui wireframe image" src="/images/wireframe/centered-paragraph.png">
    </div>
  </div>
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Internally Celled
A grid can have rows divisions only between internal rows

```html
<div class="ui internally celled grid">
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/centered-paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="row">
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="ten wide column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="three wide column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

### Content

#### Rows
A row is a horizontal grouping of columns

```html
<div class="ui three column grid">
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```

#### Columns
Columns each contain gutters giving them equal spacing from other columns.

```html
<div class="ui grid">
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="eight wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

### Variations

#### Floated
A column can sit flush against the left or right edge of a row

```html
<div class="ui grid">
  <div class="left floated five wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="right floated five wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

#### Column Width
A column can vary in width taking up more than a single grid column.

```html
<div class="ui grid">
  <div class="four wide column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="nine wide column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="three wide column">
    <img class="ui wireframe image" src="/images/wireframe/media-paragraph.png">
  </div>
</div>
```

#### Column Count
A grid can have a different number of columns per row

```html
<div class="ui grid">
  <div class="three column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="four column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="five column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Equal Width
A grid can automatically resize all elements to split the available width evenly

```html
<div class="ui equal width grid">
  <div class="column">
    <div class="ui segment">
      1
    </div>
  </div>
  <div class="eight wide column">
    <div class="ui segment">
      2
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      3
    </div>
  </div>
</div>
```

```html
<div class="ui equal width grid">
  <div class="row">
    <div class="column">
      <div class="ui segment">1</div>
    </div>
    <div class="column">
      <div class="ui segment">2</div>
    </div>
    <div class="column">
      <div class="ui segment">3</div>
    </div>
    <div class="column">
      <div class="ui segment">4</div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">1</div>
    </div>
    <div class="column">
      <div class="ui segment">2</div>
    </div>
    <div class="column">
      <div class="ui segment">3</div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">1</div>
    </div>
    <div class="column">
      <div class="ui segment">2</div>
    </div>
  </div>
</div>
```

#### Stretched
A row can stretch its contents to take up the entire column height

```html
<div class="ui three column divided grid">
  <div class="stretched row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
      <div class="ui segment">
        3
      </div>
    </div>
  </div>
</div>
```

```html
<div class="ui equal width grid">
  <div class="stretched row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="six wide column">
      <div class="ui segment">
        <img class="ui image" src="/images/wireframe/image.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
    <div class="six wide column">
      <div class="ui segment">
        <img class="ui image" src="/images/wireframe/image.png">
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        1
      </div>
      <div class="ui segment">
        2
      </div>
    </div>
  </div>
</div>
```

#### Padded
A grid can preserve its vertical and horizontal gutters on first and last columns

The following grid has vertical and horizontal gutters

```html
<div class="ui two column padded grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

The following grid has vertical gutters.

```html
<div class="ui two column vertically padded grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

The following grid has horizontal gutters

```html
<div class="ui two column horizontally padded grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
  </div>
</div>
```

#### Relaxed
A grid can increase its gutters to allow for more negative space

```html
<div class="ui four column relaxed grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
</div>
```

```html
<div class="ui four column very relaxed grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
</div>
```

#### Colored
A row or column can be colored

```html
<div class="ui five column padded grid">
  <div class="red column">Red</div>
  <div class="orange column">Orange</div>
  <div class="yellow column">Yellow</div>
  <div class="olive column">Olive</div>
  <div class="green column">Green</div>
  <div class="teal column">Teal</div>
  <div class="blue column">Blue</div>
  <div class="violet column">Violet</div>
  <div class="purple column">Purple</div>
  <div class="pink column">Pink</div>
  <div class="brown column">Brown</div>
  <div class="grey column">Grey</div>
  <div class="black column">Black</div>
</div>
```

```html
<div class="ui padded grid">
  <div class="red row">
    <div class="column">Red</div>
  </div>
  <div class="orange row">
    <div class="column">Orange</div>
  </div>
  <div class="yellow row">
    <div class="column">Yellow</div>
  </div>
  <div class="olive row">
    <div class="column">Olive</div>
  </div>
  <div class="green row">
    <div class="column">Green</div>
  </div>
  <div class="teal row">
    <div class="column">Teal</div>
  </div>
  <div class="blue row">
    <div class="column">Blue</div>
  </div>
  <div class="violet row">
    <div class="column">Violet</div>
  </div>
  <div class="purple row">
    <div class="column">Purple</div>
  </div>
  <div class="pink row">
    <div class="column">Pink</div>
  </div>
  <div class="brown row">
    <div class="column">Brown</div>
  </div>
  <div class="grey row">
    <div class="column">Grey</div>
  </div>
  <div class="black row">
    <div class="column">Black</div>
  </div>
</div>
```

#### Centered
A grid can have its columns centered

```html
<div class="ui two column centered grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="four column centered row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="four column row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

#### Text Alignment
A grid, row, or column can specify its text alignment

```html
<div class="ui center aligned three column grid">
  <div class="row">
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Cats
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Dogs
        </div>
        <div class="item">
          Poodle
        </div>
        <div class="item">
          Cockerspaniel
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Monkeys
        </div>
      </div>
    </div>
  </div>
</div>
```

```html
<div class="ui center aligned grid">
  <div class="three column row">
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Cats
        </div>
      </div>
    </div>
    <div class="left aligned column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Dogs
        </div>
        <div class="item">
          Poodle
        </div>
        <div class="item">
          Cockerspaniel
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Monkeys
        </div>
      </div>
    </div>
  </div>
  <div class="justified row">
    <div class="column">
      <p>Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other. Justified content fits exactly inside the grid column, taking up the entire width from one side to the other.</p>
    </div>
  </div>
</div>
```

```html
<div class="ui right aligned three column grid">
  <div class="row">
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Cats
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Dogs
        </div>
        <div class="item">
          Poodle
        </div>
        <div class="item">
          Cockerspaniel
        </div>
      </div>
    </div>
    <div class="column">
      <div class="ui vertical fluid menu">
        <div class="header item">
          Monkeys
        </div>
      </div>
    </div>
  </div>
</div>
```

#### Vertical Alignment
A grid, row, or column can specify its vertical alignment to have all its columns vertically centered.

```html
<div class="ui middle aligned four column centered grid">
  <div class="row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

```html
<div class="ui four column centered grid">
  <div class="top aligned row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="middle aligned row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
  <div class="bottom aligned row">
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
    <div class="column">
      <img class="ui wireframe image" src="/images/wireframe/image.png">
    </div>
  </div>
</div>
```

### Responsive Variations

#### Doubling
A grid can double its column width on tablet and mobile sizes

> A grid will round its columns to the closest reasonable value when doubling, for example a `five column grid` will use `2 mobile, 3 tablet, 5 desktop`. To force 1 column on mobile you can add `stackable`

```html
<div class="five column doubling ui grid">
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
  <div class="column">
    <img class="ui wireframe image" src="/images/wireframe/image.png">
  </div>
</div>
```

#### Stackable
A grid can have its columns stack on-top of each other after reaching mobile breakpoints

> To see a grid stack, try resizing your browser to a small width

```html
<div class="two column stackable ui grid">
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
  <div class="column">
    <div class="ui segment">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
      <img class="ui wireframe image" src="/images/wireframe/paragraph.png">
    </div>
  </div>
</div>
```

#### Reversed
A grid or row can specify that its columns should reverse order at different device sizes

> Reversed grids are compatible with `divided` grids and other complex grid types.

```html
<div class="ui computer reversed equal width grid">
  <div class="row">
    <div class="column">
      Computer A Fourth
    </div>
    <div class="column">
      Computer A Third
    </div>
    <div class="column">
      Computer A Second
    </div>
    <div class="column">
      Computer A First
    </div>
  </div>
  <div class="row">
    <div class="column">
      Computer B Fourth
    </div>
    <div class="column">
      Computer B Third
    </div>
    <div class="column">
      Computer B Second
    </div>
    <div class="column">
      Computer B First
    </div>
  </div>
</div>
```

```html
<div class="ui tablet reversed equal width grid">
  <div class="column">
    Tablet Fourth
  </div>
  <div class="column">
    Tablet Third
  </div>
  <div class="column">
    Tablet Second
  </div>
  <div class="column">
    Tablet First
  </div>
</div>
```

```html
<div class="ui mobile reversed equal width grid">
  <div class="column">
    Mobile Fourth
  </div>
  <div class="column">
    Mobile Third
  </div>
  <div class="column">
    Mobile Second
  </div>
  <div class="column">
    Mobile First
  </div>
</div>
```

```html
<div class="ui computer vertically reversed grid">
  <div class="row">
    <div class="column">Computer Row 4</div>
  </div>
  <div class="row">
    <div class="column">Computer Row 3</div>
  </div>
  <div class="row">
    <div class="column">Computer Row 2</div>
  </div>
  <div class="row">
    <div class="column">Computer Row 1</div>
  </div>
</div>
```

```html
<div class="ui tablet vertically reversed grid">
  <div class="row">
    <div class="column">Tablet Row 4</div>
  </div>
  <div class="row">
    <div class="column">Tablet Row 3</div>
  </div>
  <div class="row">
    <div class="column">Tablet Row 2</div>
  </div>
  <div class="row">
    <div class="column">Tablet Row 1</div>
  </div>
</div>
```

```html
<div class="ui mobile vertically reversed grid">
  <div class="row">
    <div class="column">Mobile Row 4</div>
  </div>
  <div class="row">
    <div class="column">Mobile Row 3</div>
  </div>
  <div class="row">
    <div class="column">Mobile Row 2</div>
  </div>
  <div class="row">
    <div class="column">Mobile Row 1</div>
  </div>
</div>
```

#### Device Visibility
A columns or row can appear only for a specific device, or screen sizes

> See container documentation for information on breakpoint calculations

```html
<div class="ui grid">
  <div class="two column large screen only row">
    <div class="column">
      <div class="ui segment">
        Large Screen
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Large Screen
      </div>
    </div>
  </div>
  <div class="two column large screen only row">
    <div class="column">
      <div class="ui segment">
        Widescreen
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Widescreen
      </div>
    </div>
  </div>
  <div class="two column mobile only row">
    <div class="column">
      <div class="ui segment">
        Mobile
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Mobile
      </div>
    </div>
  </div>
  <div class="three column row">
    <div class="computer only column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="tablet mobile only column">
      <div class="ui segment">
        Tablet and Mobile
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        All Sizes
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        All Sizes
      </div>
    </div>
  </div>
  <div class="four column computer only row">
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Computer
      </div>
    </div>
  </div>
  <div class="three column tablet only row">
    <div class="column">
      <div class="ui segment">
        Tablet
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Tablet
      </div>
    </div>
    <div class="column">
      <div class="ui segment">
        Tablet
      </div>
    </div>
  </div>
</div>
```

#### Responsive Width
A column can specify a width for a specific device

> It's recommended to use a responsive pattern like `doubling` or `stackable` to reduce complexity when designing responsively, however in some circumstances specifying exact widths for screen sizes may be necessary.

```html
<div class="ui grid">
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="sixteen wide mobile eight wide tablet four wide computer column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
</div>
```

```html
<div class="ui grid">
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
  <div class="four wide two wide large screen one wide widescreen column">
    <img src="/images/wireframe/paragraph.png" class="ui wireframe image">
  </div>
</div>
```
