## What is Flexbox?

-New feature in CSS3 that allows you to use super flexible layouts that used to be very complex and 'hacky' to make using a combination of floats and variable heights
-Makes writing a mobile responsive site incredibly easy

## Setup:
-need a parent container with children. The parent container is the 'flex container' and the children are the 'flex items'.

.parent {
  display: flex;
}

.child {

}

## Flexbox axis && flex-direction
Flexbox is all about axes

.parent {
  display: flex;
  flex-direction: row;
}

.child {

}

Have a row axis (left right) and cross axis (up down)

Default direction is row; row axis(main axis) ---> && cross axis v

flex-direction: column; row axis --> && cross axis(main axis) v

flex-direction: row-reverse; row axis(main axis) <-- && cross axis v

flex-direction: column-reverse; row axis --> && cross axis(main axis) ^

If you can't answer what your axes are, then take a step back and look at what you assigned for flex-direction

## Flex-wrap

Set the width of the child element to 300px

example:
.box {
  width: 300px;
}

See out it takes up the screen size rather than breaking to a new line? This is a huge difference between flexbox and using floats or display inline/block. It makes it incredibly easy to design your page without knowing the size of the content ahead of time.

.parent {
  display: flex;
  flex-wrap: wrap; or wrap-reverse
}


## Flex ordering
You can change the order of the flex items. This is common for making a mobile web site--sometimes the design requires the order of children to be total different.

By default the order value of a flex item is 0.

Try to figure out what this example will render:

.container {
  display: flex;
}

.box3 {
  order: 7;
}

.box1 {
  order: 2;
}

.box9 {
  order: 5;
}

Hint: flexbox will order the flex items in numerical order based on what their order property is.

## Flexbox alignment and centering with justify-content

One of the most used & important parts of flexbox.

justify-content: how are the items aligned on the main axis running left to right

.parent {
  display: flex;
  justify-content: [options]
}

options:

flex-end: starts on right hand side because that's the end of the of the main axis for this

flex-direction (default === row)

flex-start: starts on left hand side for same reason above

space-between: space them out from flex-start to flex end, this is amazing because there
would be alot of math with floats and margins otherwise

space-around: similar to space-between but gives is space on left and right of first and last flex items


Change flex-direction to column, and see how everything changes? There is no space, why is that?


We never defined the height! As a result, the flex items are taking up as much height as the content physically is.


Try changing the font size of .box to 20px, and change the height of .container to 100vh and see how that changes.



## Flexbox alignment and centering with align-items

align-items: how are the items aligned on the cross axis running top to bottom

Figure out what this code will do:
.container {
  display: flex;
  border: 10px 0 goldenrod;
  align-items: center;
  height: 80vh;
}

align-items: stretch === having no align-items at all, the items will stretch to the entirety of the parent element

align-items: flex-start

align-items: flex-end

align-items: baseline === will align according to the bottom of the content in the flex item divs, in our example it will align by the baseline of the numbers.

Add this code to see it in action:

.box2 {
  height: 30px;
}
.box3 {
  height: 60px;
}
.box4 {
  height: 100px;
}
.box5 {
  height: 200px;
}
.box6 {
  height: 10px;
}

What will happen if we change flex-direction to column?

## Flexbox alignment and centering with align-content
- Similar to align-content and and align-items, but puts space between multiple lines of flex items. Use this code to get started in our example:

.container {
  display: flex;
  border: 10px solid goldenrod;
  height: 100vh;
  Flex-wrap: wrap;
}

.box {
  width: 33.33333333%
}


align-content: stretch (default)

align-content: space-between

align-content: space-around

align-content: center;

What happens if you combine justify-content: center in the parent element with align-content: center?

## Flexbox alignment and centering with align-self

- This is a flex property applied to the child to overwrite alignment on the parent container for that specific child.

Try this code:

.container {

  display: flex;

  border: 10px solid goldenrod;

  height: 100vh;

  align-items: flex-start;

}

.box {

  width: 33.3333%;

}

.box2 {

  padding-bottom: 200px;

}

.box6 {

  padding-bottom: 0;

}

.box9 {

  padding-bottom: 50px;

  align-self: flex-end; | stretch | baseline

}

- See how box 9 changes?

## Understanding Flexbox sizing with the flex property.

- Comment out boxs 7 - 10 so there are 6 boxes

- Flexbox intelligently figures out what to do when when there is not enough space or what to do with extra space.

Try this code:

.container {

  display: flex;

}

.box {

  flex: 1;

}

- Notice the change that happens to the children? They each spread out to take up the width of the flex container


- Try this code:


.box2 {

  flex: 2;

}

.box4 {

  flex: 3;

}


- Cool how everything works in ratios right?



#### Follow up resources

https://css-tricks.com/snippets/css/a-guide-to-flexbox/ (good visual representation of what each flex property does)


http://flexbox.io/ (free 20 video courses)

http://flexboxfroggy.com/ (fun game to learn flexbox)
