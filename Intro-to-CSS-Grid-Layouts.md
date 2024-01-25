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
    /* Longhand.
    grid-template-rows: 100px <1st row height> 200px <2nd row height>;
    grid-template-columns: 200px <1st column width> auto <takes remaing width> 150px <3rd column width>; 
    */
    
    /* Shorthand */ grid-template: 100px /* 1st row height */ 200px /* 2nd row height */ / 200px /* 1st column width */ auto /* takes remaing width */ 150px /* 3rd column width */; 
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
.grid div:nth-child(2){
    /* re-arranges items in the horizontal grid line */
    grid-row-start: 2; 
    grid-row-end: 3;
    /* re-arranges items in the vertical grid line */
    grid-column-start: 1; 
    grid-column-end: 2;
}

.grid div:nth-child(5){
   /* Shorthand of the above concept */
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
.grid div:nth-child(1){
    grid-row: auto /* wherever the row starts */ / span 2; /* spans the height of the column by 2 rows */
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
    grid-template: 
    /* Provides an alias for the first horizontal gridline*/ [row1-start]100px 
    /* Provides an alias for the 2nd horizontal gridline*/[row1-end row2-start]200px 
    [row2-end] / 
    /* Provides an alias for the first vertical gridline */ [col1-start]200px 
    /* Provides an alias for the 2nd vertical gridline */[col1-end col2-start]auto 
    /* Provides an alias for the 3rd vertical gridline */[col-2-end]150px; 
}

/* Applicability */
.grid div:nth-child(5){
    grid-row: row1-start / row2-end;
    grid-column: col1-start / col2-end;
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
.grid{
    display: grid; 
    grid-template: 100px 200px / 200px auto  150px ; 
    /* Provides gutters in the horizontal line 
    grid-row-gap: 10px; */
    /* Provides gutters in the vertical line 
    grid-column-gap: 10px; */
    /* Shorthand */
    grid-gap: 10px 10px; 
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
## Source-order Independence; order.

```CSS
/* Source-Order: Independence-order */
.grid{
    display: grid; 
    grid-template: 100px 200px / 200px auto  150px ; 
    grid-gap: 10px 10px; 
}

/* Flexbox order property applicable */
.grid div:nth-child(6){
    order: -1;
}

.grid div:nth-child(3){
    order: 1;
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
# Section #4: Using Grid Areas, Equal Sizes, repeat()& minmax().
 ## Using Grid Areas: grid area.
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
    grid-area: 2 / 1 / 4 / 2; /* grid-row-start / grid-column-start / grid-row-end / grid-column-end */
 /* grid-row-start: 2;
    grid-row-end: 3;
    grid-column-start: 1;
    grid-column-end: 2; */
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
 ## Using Grid Areas: grid-template-area.
```CSS
.grid{
    display: grid;
    grid-template: 100px 100px 100px/200px auto 150px;
    grid-template-areas: 
    ". E ."
    "B C C"
    "F F F"
}

.grid div:nth-child(1){
    grid-area: A;
}

.grid div:nth-child(2){
    grid-area: B;
}

.grid div:nth-child(3){
    grid-area: C;
}

.grid div:nth-child(4){
    grid-area: D;
}

.grid div:nth-child(5){
    grid-area: E;
}

.grid div:nth-child(6){
    grid-area: F;
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
 ## Repeating Rows and Columns: repeat().
```CSS
.grid{
    display: grid;
    grid-template: 100px 100px 100px/repeat(12, [small] 20px [large] 40px);
}

.grid div:nth-child(1){
    grid-column: auto /span 12; 

}

.grid div:nth-child(2){
    grid-column: small 1 /large 3; 
}

.grid div:nth-child(3){
    grid-column: auto /span 12; 
}

.grid div:nth-child(4){
    grid-column: auto /span 12; 
}

.grid div:nth-child(5){
    grid-column: auto /span 12; 
}

.grid div:nth-child(6){
    grid-column: auto /span 12; 
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
## The Fr Unit.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
 /* grid-template: 100px 100px 100px/100px 2fr 1fr; */
    grid-template: 100px 100px 100px /repeat(6, 1fr);
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
## Defining Minimum and Maximum Sizes: minmax().
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: minmax(100px, 200px) / repeat(6, minmax(100px, 1fr));
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
## Auto-Filling a Grid with Rows and Columns: repeat(auto-fill)
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 100px 100px 100px /repeat(auto-fill, minmax(auto, 200px));
 /* grid-template: 100px 100px 100px /repeat(auto-fill, minmax(100px, auto)<----Big nono!*/);
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
## repeat(auto-fit)
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 100px 100px 100px /repeat(auto-fit, minmax(100px, 1fr));
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
# Section 5: Justifying the Grid Container and Grid Items. 

## Justifying Items Horizontally: justify-items.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 100px 100px 100px /repeat(auto-fit, minmax(100px, 1fr));
    justify-items: start; /* end, center, stretch */ 
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
## Align Items Vertically: align-items.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 100px 100px 100px /repeat(auto-fit, minmax(100px, 1fr));
    align-items: center; /* end, center, stretch */ 
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
## Justifying the Container: justify-content.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 100px 100px 100px / 200px auto;
    justify-content: start; /*stretch, end, space-around, space between, space-evenly */
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
## Aligning the Container: align-content.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 100px 100px 100px / 200px auto;
    align-content: start; /*stretch, end, space-around, space between, space-evenly */
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
## Overriding Alignments: justify-self & align-self.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 150px 150px / 200px 200px 200px;
    border: 1px solid #FFF;
    padding: 10px;
    height: 400px;
    justify-content: center;
    align-content: center;

}
.grid div:nth-child(1){
    justify-self: start; /* stretch, center */
}

.grid div:nth-child(3){
    justify-self: end; /* stretch, center */
    align-self: end;
}

.grid div:nth-child(5){
    justify-self: center; /* stretch, center */
    align-self: start;
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
# Section #6: The Implicit Grid and Grid Flow.
## The Implicit Grid: grid-auto-rows & grid-auto-columns.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 150px 150px / 150px 150px; /* explicit row/column sizes */
    grid-auto-rows: 100px; /* implicit row size */
    grid-auto-columns: 150px;/* implicit column size*/
}

.grid div:nth-child(2){
    grid-column: 2 / span 3;
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
## Flow for the Implicit Grid: grid-auto-flow.
```CSS
.grid{
    display: grid;
    grid-gap: 10px;
    grid-template: 150px 150px / 150px 150px;
 /* grid-auto-rows: 100px;
    grid-auto-columns: 150px; */
    grid-auto-flow: row dense; /* column, row */
}

.grid div:nth-child(2){
    /* grid-column: 1 / span 3; */
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
## Shorthand when using grid.
```CSS
.grid{
    display: grid;
    grid: 150px 150px / auto-flow 150px; 
     /* Equivalent to:
    grid-auto-flow: column;
    grid-template-columns: none; (default)
    grid-auto-columns: 150px;
    grid-template-rows: none;
    grid-auto-rows: 150px;
    */
    grid-gap: 10px; /* <-- below grid property. */
}

.grid div:nth-child(2){
    grid-column: 1 / span 3;
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

## Placeholder
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
