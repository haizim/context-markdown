# Table

A table displays a collections of data grouped into rows

## Types

#### Table
A standard table
> Tables will automatically stack their layouts for mobile devices. To disable this behavior, use the `unstackable` variation or `tablet stackable` to allow responsive adjustments for tablet.
```html
<table class="ui celled table">
  <thead>
    <th>Name</th>
    <th>Age</th>
    <th>Job</th>
  </thead>
  <tbody>
    <tr>
      <td data-label="Name">James</td>
      <td data-label="Age">24</td>
      <td data-label="Job">Engineer</td>
    </tr>
    <tr>
      <td data-label="Name">Jill</td>
      <td data-label="Age">26</td>
      <td data-label="Job">Engineer</td>
    </tr>
    <tr>
      <td data-label="Name">Elyse</td>
      <td data-label="Age">24</td>
      <td data-label="Job">Designer</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui celled padded table">
  <thead>
    <th class="single line">Evidence Rating</th>
    <th>Effect</th>
    <th>Efficacy</th>
    <th>Consensus</th>
    <th>Comments</th>
  </thead>
  <tbody>
    <tr>
      <td>
        <h2 class="ui center aligned header">A</h2>
      </td>
      <td class="single line">
        Power Output
      </td>
      <td>
        <div class="ui star rating" data-rating="3" data-max-rating="3"></div>
      </td>
      <td class="right aligned">
        80% <br>
        <a href="#">18 studies</a>
      </td>
      <td>Creatine supplementation is the reference compound for increasing muscular creatine levels; there is variability in this increase, however, with some nonresponders.</td>
    </tr>
    <tr>
      <td>
        <h2 class="ui center aligned header">A</h2>
      </td>
      <td class="single line">
        Weight
      </td>
      <td>
        <div class="ui star rating" data-rating="3" data-max-rating="3"></div>
      </td>
      <td class="right aligned">
        100% <br>
        <a href="#">65 studies</a>
      </td>
      <td>Creatine is the reference compound for power improvement, with numbers from one meta-analysis to assess potency</td>
    </tr>
  </tbody>
  <tfoot>
    <th colspan="5">
      <div class="ui right floated pagination menu">
        <a class="icon item">
          <i class="left chevron icon"></i>
        </a>
        <a class="item">1</a>
        <a class="item">2</a>
        <a class="item">3</a>
        <a class="item">4</a>
        <a class="icon item">
          <i class="right chevron icon"></i>
        </a>
      </div>
    </th>
  </tfoot>
</table>
```
```html
<table class="ui very basic collapsing celled table">
  <thead>
    <th>Employee</th>
    <th>Correct Guesses</th>
  </thead>
  <tbody>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/lena.png" class="ui mini rounded image">
          <div class="content">
            Lena
            <div class="sub header">Human Resources
          </div>
        </div>
      </td>
      <td>
        22
      </td>
    </tr>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/matthew.png" class="ui mini rounded image">
          <div class="content">
            Matthew
            <div class="sub header">Fabric Design
          </div>
        </div>
      </td>
      <td>
        15
      </td>
    </tr>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/lindsay.png" class="ui mini rounded image">
          <div class="content">
            Lindsay
            <div class="sub header">Entertainment
          </div>
        </div>
      </td>
      <td>
        12
      </td>
    </tr>
    <tr>
      <td>
        <h4 class="ui image header">
          <img src="/images/avatar2/small/mark.png" class="ui mini rounded image">
          <div class="content">
            Mark
            <div class="sub header">Executive
          </div>
        </div>
      </td>
      <td>
        11
      </td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui celled striped table">
  <thead>
    <th colspan="3">
      Git Repository
    </th>
  </thead>
  <tbody>
    <tr>
      <td class="collapsing">
        <i class="folder icon"></i> node_modules
      </td>
      <td>Initial commit</td>
      <td class="right aligned collapsing">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> test
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> build
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="file outline icon"></i> package.json
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="file outline icon"></i> Gruntfile.js
      </td>
      <td>Initial commit</td>
      <td class="right aligned">10 hours ago</td>
    </tr>
  </tbody>
</table>
```

#### Definition
A table may be formatted to emphasize a first column that defines a rows content
> Definition tables are designed to display on a single background color. You can adjust this by changing `@definitionPageBackground`, or specifying a background color on the first cell
```html
<table class="ui definition table">
  <thead>
    <th></th>
    <th>Arguments</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>reset rating</td>
      <td>None</td>
      <td>Resets rating to default value</td>
    </tr>
    <tr>
      <td>set rating</td>
      <td>rating (integer)</td>
      <td>Sets the current star rating to specified value</td>
    </tr>
</table>
```
```html
<table class="ui compact celled definition table">
  <thead>
    <tr>
      <th></th>
      <th>Name</th>
      <th>Registration Date</th>
      <th>E-mail address</th>
      <th>Premium Plan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
  <tfoot class="full-width">
    <tr>
      <th></th>
      <th colspan="4">
        <div class="ui right floated small primary labeled icon button">
          <i class="user icon"></i> Add User
        </div>
        <div class="ui small button">
          Approve
        </div>
        <div class="ui small  disabled button">
          Approve All
        </div>
      </th>
    </tr>
  </tfoot>
</table>
```

#### Structured
A table can be formatted to display complex structured data
> UI tables use `border-collapse: separate` to allow for tables to receive styles that cannot usually be applied to tables like `border-radius`. However this can cause some cell borders to appear missing with complex layouts that use `rowspan` or `colspan` and rows with varying column count.
> `ui structured table` does not support some style features, but can correctly display all valid HTML table content.
```html
<table class="ui celled structured table">
  <thead>
    <tr>
      <th rowspan="2">Name</th>
      <th rowspan="2">Type</th>
      <th rowspan="2">Files</th>
      <th colspan="3">Languages</th>
    </tr>
    <tr>
      <th>Ruby</th>
      <th>JavaScript</th>
      <th>Python</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alpha Team</td>
      <td>Project 1</td>
      <td class="right aligned">2</td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td rowspan="3">Beta Team</td>
      <td>Project 1</td>
      <td class="right aligned">52</td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>Project 2</td>
      <td class="right aligned">12</td>
      <td></td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>Project 3</td>
      <td class="right aligned">21</td>
      <td class="center aligned">
        <i class="large green checkmark icon"></i>
      </td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>
```

## States

#### Positive / Negative
A cell or row may let a user know whether a value is good or bad
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>No Name Specified</td>
      <td>Unknown</td>
      <td class="negative">None</td>
    </tr>
    <tr class="positive">
      <td>Jimmy</td>
      <td><i class="icon checkmark"></i> Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Unknown</td>
      <td class="positive"><i class="icon close"></i> Requires call</td>
    </tr>
    <tr class="negative">
      <td>Jill</td>
      <td>Unknown</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

### Cells

#### Error
A cell or row may call attention to an error or a negative value
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>No Name Specified</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr class="error">
      <td>Jimmy</td>
      <td>Cannot pull data</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="error"><i class="attention icon"></i> Classified</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Warning
A cell or row may warn a user
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>No Name Specified</td>
      <td>Unknown</td>
      <td>None</td>
    </tr>
    <tr class="warning">
      <td>Jimmy</td>
      <td><i class="attention icon"></i> Requires Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Unknown</td>
      <td class="warning"><i class="attention icon"></i> Hostile</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Unknown</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Active
A cell or row can be active or selected by a user
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr class="active">
      <td>John</td>
      <td>Selected</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td class="active">Jill</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Disabled
A cell can be disabled
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr class="disabled">
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Selected</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td class="disabled">Jill</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

## Variations

#### Single Line
A table can specify that its cell contents should remain on a single line, and not wrap.
```html
<table class="ui single line table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Registration Date</th>
      <th>E-mail address</th>
      <th>Premium Plan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>
```

#### Fixed
A table can use `table-layout: fixed` a special faster form of table rendering that does not resize table cells based on content.
```html
<table class="ui fixed table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>John is an interesting boy but sometimes you don't really have enough room to describe everything you'd like</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Jamie is a kind girl but sometimes you don't really have enough room to describe everything you'd like</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Jill is an alright girl but sometimes you don't really have enough room to describe everything you'd like</td>
    </tr>
  </tbody>
</table>
```
> Fixed `single line` tables will automatically ensure content that does not fit in a single line will receive "..." ellipsis
```html
<table class="ui fixed single line celled table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td title="This is much too long to fit I'm sorry about that">This is much too long to fit I'm sorry about that</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Shorter description</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>Shorter description</td>
    </tr>
  </tbody>
</table>
```

#### Stacking
A table can specify how it stacks table content responsively
```html
<table class="ui unstackable table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui tablet stackable table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```

#### Selectable Row
A table can have its rows appear selectable
```html
<table class="ui selectable celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>No Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
    <tr class="warning">
      <td>John</td>
      <td>No Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="positive">Approved</td>
      <td class="warning">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td class="negative">Denied</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui selectable inverted table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```

#### Selectable Cell
A table cell can be selectable
> Using an `a` link inside a selectable cell will automatically make the hit box the entire cell area. By default links will inherit their cell color.
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Edit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>No Action</td>
      <td class="selectable">
        <a href="#">Edit</a>
      </td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="selectable">
        <a href="#">Edit</a>
      </td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="selectable">
        <a href="#">Edit</a>
      </td>
    </tr>
    <tr class="warning">
      <td>John</td>
      <td>No Action</td>
      <td class="selectable warning">
        <a href="#">Requires change</a>
      </td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="positive">Approved</td>
      <td class="selectable positive">
        <a href="#">Approve</a>
      </td>
    </tr>
    <tr>
      <td>Jill</td>
      <td class="negative">Denied</td>
      <td class="selectable negative">
        <a href="#">Remove</a>
      </td>
    </tr>
  </tbody>
</table>
```

#### Vertical Alignment
A table header, row, or cell can adjust its vertical alignment
```html
<table class="ui striped table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr class="top aligned">
      <td>John</td>
      <td>Approved</td>
      <td class="top aligned">
        Notes<br>
        1<br>
        2<br>
      </td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="bottom aligned">Approved</td>
      <td>
        Notes<br>
        1<br>
        2<br>
      </td>
    </tr>
  </tbody>
</table>
```

#### Text Alignment
A table header, row, or cell can adjust its text alignment
```html
<table class="ui striped table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th class="right aligned">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr class="center aligned">
      <td>John</td>
      <td>Approved</td>
      <td class="right aligned">None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td class="right aligned">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td class="right aligned">None</td>
    </tr>
  </tbody>
</table>
```

#### Striped
A table can stripe alternate rows of content with a darker color to increase contrast
```html
<table class="ui striped table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Date Joined</th>
      <th>E-mail</th>
      <th>Called</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
  </tbody>
</table>
```

#### Celled
A table may be divided each row into separate cells
```html
<table class="ui celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```

#### Basic
A table can reduce its complexity to increase readability.
```html
<table class="ui basic table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui very basic table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
```

#### Collapsing Cell
A cell can be collapsing so that it only uses as much space as required
> To ensure icons don't wrap to a separate line you must either specify collapsing on the widest row in the collapsing column, or on all rows
```html
<table class="ui table">
  <tbody>
    <tr>
      <td class="collapsing">
        <i class="folder icon"></i> node_modules
      </td>
      <td>Initial commit</td>
      <td>10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> test
      </td>
      <td>Initial commit</td>
      <td>10 hours ago</td>
    </tr>
    <tr>
      <td>
        <i class="folder icon"></i> build
      </td>
      <td>Initial commit</td>
      <td>10 hours ago</td>
    </tr>
  </tbody>
</table>
```

#### Column Count
A table can specify its column count to divide its content evenly
```html
<table class="ui five column table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Age</th>
    <th>Gender</th>
    <th>Notes</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>22</td>
      <td>Male</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>32</td>
      <td>Male</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>22</td>
      <td>Female</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
    <th></th>
    <th></th>
  </tfoot>
</table>
```

#### Column Width
A table can specify the width of individual columns independently.
> Tables use a 16 column grid similar to ui grid
```html
<table class="ui table">
  <thead>
    <th class="ten wide">Name</th>
    <th class="six wide">Status</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
  </tfoot>
</table>
```

#### Collapsing
A table can be collapsing, taking up only as much space as its rows.
```html
<table class="ui collapsing table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```

#### Colored
A table can be given a color to distinguish it from other tables.
```html
<table class="ui red table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui orange table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui yellow table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui olive table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui green table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui teal table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui blue table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui violet table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui purple table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui pink table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui grey table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui black table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
```

#### Inverted
A table's colors can be inverted
```html
<table class="ui inverted table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```
```html
<table class="ui inverted red table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted orange table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted yellow table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted olive table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted green table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted teal table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted blue table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted violet table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted purple table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted pink table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted brown table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
<table class="ui inverted grey table">
  <thead>
    <th>Food</th>
    <th>Calories</th>
    <th>Protein</th>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>200</td>
      <td>0g</td>
    </tr>
    <tr>
      <td>Orange</td>
      <td>310</td>
      <td>0g</td>
    </tr>
  </tbody>
</table>
```

#### Sortable
A table may allow a user to sort contents by clicking on a table header.
> Adding the class `ascending` or `descending` to the `th` will show the user the sorting direction. This example uses a modified version of the kylefox's tablesort plugin to provide the proper class names. To make sortable tables work, include this javascript into your page and call `$('table').tablesort()` when the DOM is ready.
```html
<table class="ui sortable celled table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>No Action</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td class="positive">Approved</td>
      <td class="warning">Requires call</td>
    </tr>
    <tr>
      <td>Jill</td>
      <td class="negative">Denied</td>
      <td>None</td>
    </tr>
  </tbody>
  <tfoot>
    <th>3 People</th>
    <th>2 Approved</th>
    <th></th>
  </tfoot>
</table>
```

#### Full-Width Header / Footer
A definition table can have a full width header or footer, filling in the gap left by the first column
```html
<table class="ui compact celled definition table">
  <thead class="full-width">
    <tr>
      <th></th>
      <th>Name</th>
      <th>Registration Date</th>
      <th>E-mail address</th>
      <th>Premium Plan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>John Lilki</td>
      <td>September 14, 2013</td>
      <td>jhlilk22@yahoo.com</td>
      <td>No</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jamie Harington</td>
      <td>January 11, 2014</td>
      <td>jamieharingonton@yahoo.com</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td class="collapsing">
        <div class="ui fitted slider checkbox">
          <input type="checkbox"> <label></label>
        </div>
      </td>
      <td>Jill Lewis</td>
      <td>May 11, 2014</td>
      <td>jilsewris22@yahoo.com</td>
      <td>Yes</td>
    </tr>
  </tbody>
  <tfoot class="full-width">
    <tr>
      <th></th>
      <th colspan="4">
        <div class="ui right floated small primary labeled icon button">
          <i class="user icon"></i> Add User
        </div>
        <div class="ui small  button">
          Approve
        </div>
        <div class="ui small  disabled button">
          Approve All
        </div>
      </th>
    </tr>
  </tfoot>
</table>
```

#### Padded
A table may sometimes need to be more padded for legibility
```html
<table class="ui padded table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>He is a very nice guy and I enjoyed talking to him on the telephone. I hope we get to talk again.</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Jamie was not interested in purchasing our product.</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui very padded table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>He is a very nice guy and I enjoyed talking to him on the telephone. I hope we get to talk again.</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Jamie was not interested in purchasing our product.</td>
    </tr>
  </tbody>
</table>
```

#### Compact
A table may sometimes need to be more compact to make more rows visible at a time
```html
<table class="ui compact table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
  </tbody>
</table>
```
```html
<table class="ui very compact table">
  <thead>
    <th>Name</th>
    <th>Status</th>
    <th>Another Status</th>
    <th>Notes</th>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
  </tbody>
</table>
```

#### Size
A table can also be small or large
```html
<table class="ui small table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Approved</td>
      <td>None</td>
    </tr>
    <tr>
      <td>Jamie</td>
      <td>Approved</td>
      <td>Requires call</td>
    </tr>
  </tbody>
</table>
```
