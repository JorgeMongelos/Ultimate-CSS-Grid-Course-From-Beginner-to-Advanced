# Section #3: Defining and Using CSS Grids.

## Enabling CSS Grid with display: grid

```CSS
.grid{
    display: grid;
}
```
```HTML
<!DOCTYPE html>
<html>
  <head>
      <title>Ultimate CSS Grid Course, (c) Peter Sommerhoff</title>
      <link rel="stylesheet" href="css/base.css">
      <link rel="stylesheet" href="css/main.css">
      <!-- Remove this line for offline development: -->
      <link href="https://fonts.googleapis.com/css?family=Ubuntu:300" rel="stylesheet">
  </head>
  <body>
    <h2>Ultimate CSS Grid Course</h2>
    <p>This is the template you can use to follow along the course.</p>
    <div>
      <div class="grid">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
        <div>Item 4</div>
        <div>Item 5</div>
        <div>Item 6</div>
      </div>
    </div>
  </body>
</html>
```
## Defining the grid: grid-template-rows & grid-template-colums.

```CSS
.grid{
    display: grid;
/*  grid-template-rows: 100px 200px ;
    grid-template-columns: 200px auto 150px; */
    grid-template: 100px 200px/200px auto 150px; /* shorthand for grid-template columns and rows */
}
```
```HTML
<!DOCTYPE html>
<html>
  <head>
      <title>Ultimate CSS Grid Course, (c) Peter Sommerhoff</title>
      <link rel="stylesheet" href="css/base.css">
      <link rel="stylesheet" href="css/main.css">
      <!-- Remove this line for offline development: -->
      <link href="https://fonts.googleapis.com/css?family=Ubuntu:300" rel="stylesheet">
  </head>
  <body>
    <h2>Ultimate CSS Grid Course</h2>
    <p>This is the template you can use to follow along the course.</p>
    <div>
      <div class="grid">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
        <div>Item 4</div>
        <div>Item 5</div>
        <div>Item 6</div>
      </div>
    </div>
  </body>
</html>
```
## Arranging Grid Items: grid-row-start/end & grid-column-start/end.

```CSS
/* Put your code here */
.grid{
    display: grid;
    grid-template: 100px 200px/200px auto 150px;
}

/* Longhand */
.grid div:nth-child(2){
    grid-row-start: 2;
    grid-row-end: 3;
    grid-column-start: 1;
    grid-column-end: 2;
}

/* Shorthand */
.grid div:nth-child(5){
    grid-row: 1 / 2;
    grid-column: 1 / 2;
}
```
```HTML
<!DOCTYPE html>
<html>
  <head>
      <title>Ultimate CSS Grid Course, (c) Peter Sommerhoff</title>
      <link rel="stylesheet" href="css/base.css">
      <link rel="stylesheet" href="css/main.css">
      <!-- Remove this line for offline development: -->
      <link href="https://fonts.googleapis.com/css?family=Ubuntu:300" rel="stylesheet">
  </head>
  <body>
    <h2>Ultimate CSS Grid Course</h2>
    <p>This is the template you can use to follow along the course.</p>
    <div>
      <div class="grid">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
        <div>Item 4</div>
        <div>Item 5</div>
        <div>Item 6</div>
      </div>
    </div>
  </body>
</html>
```
## Spanning a Fixed Number of Rows or Columns: span

```CSS
.grid{
    display: grid;
    grid-template: 100px 200px/200px auto 150px;
}

.grid div:nth-child(1){
    grid-row: auto / span 2;
}

/* Longhand */
.grid div:nth-child(2){
    grid-row-start: 2;
    grid-row-end: 3;
    grid-column-start: 1;
    grid-column-end: 2;
}

/* Shorthand */
.grid div:nth-child(5){
    grid-row: 1 / 2;
    grid-column: 1 / 2;
}
```
```HTML
<!DOCTYPE html>
<html>
  <head>
      <title>Ultimate CSS Grid Course, (c) Peter Sommerhoff</title>
      <link rel="stylesheet" href="css/base.css">
      <link rel="stylesheet" href="css/main.css">
      <!-- Remove this line for offline development: -->
      <link href="https://fonts.googleapis.com/css?family=Ubuntu:300" rel="stylesheet">
  </head>
  <body>
    <h2>Ultimate CSS Grid Course</h2>
    <p>This is the template you can use to follow along the course.</p>
    <div>
      <div class="grid">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
        <div>Item 4</div>
        <div>Item 5</div>
        <div>Item 6</div>
      </div>
    </div>
  </body>
</html>
```
## Naming Grid Lines.

```CSS
.grid{
    display: grid;
    grid-template: [row1-start]100px [row1-end row2-start]200px/200px auto 150px;
}

.grid div:nth-child(1){
    grid-row: auto / span 2;
}

/* Longhand */
.grid div:nth-child(2){
    grid-row-start: row2-start;
    grid-row-end: 3;
    grid-column-start: 1;
    grid-column-end: 2;
}

/* Shorthand */
.grid div:nth-child(5){
    grid-row: row1-start / row1-end;
    grid-column: 1 / 2;
}
```
```HTML
<!DOCTYPE html>
<html>
  <head>
      <title>Ultimate CSS Grid Course, (c) Peter Sommerhoff</title>
      <link rel="stylesheet" href="css/base.css">
      <link rel="stylesheet" href="css/main.css">
      <!-- Remove this line for offline development: -->
      <link href="https://fonts.googleapis.com/css?family=Ubuntu:300" rel="stylesheet">
  </head>
  <body>
    <h2>Ultimate CSS Grid Course</h2>
    <p>This is the template you can use to follow along the course.</p>
    <div>
      <div class="grid">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
        <div>Item 4</div>
        <div>Item 5</div>
        <div>Item 6</div>
      </div>
    </div>
  </body>
</html>
```
## Defining Gutters: grid-row-gap & grid column gap.

```CSS

```
```HTML
<!DOCTYPE html>
<html>
  <head>
      <title>Ultimate CSS Grid Course, (c) Peter Sommerhoff</title>
      <link rel="stylesheet" href="css/base.css">
      <link rel="stylesheet" href="css/main.css">
      <!-- Remove this line for offline development: -->
      <link href="https://fonts.googleapis.com/css?family=Ubuntu:300" rel="stylesheet">
  </head>
  <body>
    <h2>Ultimate CSS Grid Course</h2>
    <p>This is the template you can use to follow along the course.</p>
    <div>
      <div class="grid">
        <div>Item 1</div>
        <div>Item 2</div>
        <div>Item 3</div>
        <div>Item 4</div>
        <div>Item 5</div>
        <div>Item 6</div>
      </div>
    </div>
  </body>
</html>
``` 

## Placeholder

```CSS

```
```HTML
```
 
## Useful samples

```CSS

```
```HTML
<table>
    <thead>
    </thead>
    <tbody>
      <tr>
        <td></td>
        <td>
          <ul>
            <li></li>
          </ul>
      </td>
      </tr>
    </tbody>
</table> 
```