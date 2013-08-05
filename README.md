Sass Adaptive grid
==================

Here's my take on a sass powered adaptive grid.
Basically it's heavily inspired by [Framelessgrid](http://framelessgrid.com) and [Neat](http://neat.bourbon.io).
Framelessgrid is more a concept rather than a grid framework, whereas Neat is a very powerful fluid grid system writte in SASS.
I really appreciate both the the Frameless philosophy and how Neat is structured. It's very flexible and offers a wide range of responsive solutions with a minimal effort.

Getting started
================

Importing the grid
------------------

Start with an empty `scss` file where you import the main grid file:

	@import 'adapt/adapt';


Defining the grid
-----------------

First step is to define some settings for your grid. 
Basically you have these default variables:

	// values in px(s)
	$column: 30 !default;                     // column width
	$gutter: 20 !default;                     // space between columns
	$grid-columns: 24 !default;               // number of columns (max width calculated dinamycally)
	$border-box-sizing: true !default;        // make elements have a border-box model
	$default-feature: max-width;              // default feature type for media query
	$default-layout-direction: LTR !default;  // default layout direction
	$base-size: 16 !default;                  // base size for calculating ems

In order to override values, place your settings before importing the grid:

	$column: 40;
	$gutter: 10;
	// ...
	@import "adapt/adapt";


Defining columns
----------------

You then have access to some mixins that help you structuring your grid:
		
	// it define the main container, whose size is the sum of all columns+gutter
	@mixin container()

	// it define a self-clearing row
	@mixin row()

	// it defines a column of `n` columns width
	@mixin span-column(n)

	// it defines how to determine last-child of a set of columns
	// in this case is the `nth(2)`
	@mixin omega(2n)


Defining breakpoints
--------------------

In order to make your grid adapt to the viewport I preferer you'd rather want to think in terms of number of visible columns.
Then you'll make your container max-width equal to the number of visible columns you want.


TODO
----
1. Add SASS tests
2. Make convenient mixins to apply media-queries


Examples
--------

Check out the `example/` folder.


Credits
-------

Some functions were taken from [Neat](http://neat.bourbon.io).
Grid concept came from [Framelessgrid](http://framelessgrid.com)