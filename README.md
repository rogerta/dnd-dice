# D&D Dice Web Components

This package contains Polymer-based web components for including D&D style dice rolling into web applications. Use the fully-featured panel to easily add dice rolling, or use the individual components to build just the UI you need.

Four components are included:

### D&D Dice Result (<dnd-dice-result>)

A component that shows a random result of rolling dice. This is essentially a
large button that shows the result along with a text input field to specify
what dice to roll. Click the button to roll again.

### Standard D&D Dice Grid (<dnd-dice-standard>)

A component that shows a grid of buttons for rolling standard D&D dice like d6
or d20. Clicking a button fires an event. Quickly multi-clicking a button fires
an event that specifies the corresponding multiple number of dice to roll.

### Preset D&D Dice Grid (<dnd-dice-preset>)

A component that shows a grid of buttons for rolling custom D&D dice, like
2d4-1 or 3d6. Clicking or long-clicking a button fires an event. Clicking is
often used to roll the dice, while long-clicking is used to preset the button to
a given custom dice specification.

### Complete D&D Dice Panel (<dnd-dice-panel>)

A compoment that puts together all the above into a full featured UI for
A rolling dice.

## Dice Specification

A dice specification is a string of the form **NdD+M**, which is interpreted to
mean: roll the **D** die **N** times, summing the rolls together, and add the
modifier **M** to this sum. To subtract a modifier instead, the specification
has the form **NdD-M**. The numbers **N**, **D**, and **M** must be positive
numbers from 1 to 100. Here are some examples:

**1d20**
Roll the die with twenty sides once. This will result in a number from 1 to 20.

**3d6**
Roll the die with six sides three times adding the rolls together. This will
result in a number from 3 to 18.

**2d4-1**
Roll the die with four sides twice adding the rolls together, then subtract 1.
This will result in a number from 1 to 7.  Its possible to leave out parts of
the specification. For example, if N is omitted it defaults to 1. If D is
omitted it defaults to 8. If M is omitted it defaults to 0. The following are
valid specifications:

**d20**
Roll the die with twenty sides once.

**2d**
Roll the die with eight sides twice adding the rolls together.

**1+1**
Roll the die with eight sides once, then add 1. That is, if D then d can also
be omitted.

**d4**2
Roll the die with 42 sides once. Probably not very useful for D&D.

# Demos

See [demos](http://dnd-tools.appspot.com/components/dnd-dice/demo.html) of all
the components.

