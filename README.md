# D&D Dice Web Components

This package contains [Polymer](https://www.polymer-project.org/)-based
[web components](http://webcomponents.org/) for including
[D&D](http://www.wizards.com/dnd/) style dice rolling into web applications.
Use the fully-featured panel to easily add dice rolling, or use the individual
components to build just the UI you need.

Five components are included:

### D&D Dice Result `<dnd-dice-result>`
A component that shows a random result of rolling dice. This is essentially a
large button that shows the result along with a text input field to specify
what dice to roll. Click the button to roll again.

### Standard D&D Dice Grid `<dnd-dice-standard>`
A component that shows a grid of buttons for rolling standard D&D dice like d6
or d20. Clicking a button fires an event. Quickly multi-clicking a button fires
an event that specifies the corresponding multiple number of dice to roll.

### Preset D&D Dice Grid `<dnd-dice-preset>`
A component that shows a grid of buttons for rolling custom D&D dice, like
2d4-1 or 3d6. Clicking or long-clicking a button fires an event. Clicking is
often used to roll the dice, while long-clicking is used to preset the button to
a given custom dice specification.

### D&D Dice Helper `<dnd-dice-helper>`
A component that contains helper functions to parse and unparse dice
specifications as well as generating random rolls of dice.

### Complete D&D Dice Panel `<dnd-dice-panel>`
A component that puts together all the above into a full featured UI for
rolling dice.

See the
[API documentation](http://rogerta.github.io/dnd-dice/components/dnd-dice/)
for a full description of each component.

## Simple Dice Specification

A dice specification is a string of the form **NdD+M**, which is interpreted to
mean: roll the **D** die **N** times, summing the rolls together, and add the
modifier **M** to this sum. To subtract a modifier instead, the specification
has the form **NdD-M**. The numbers **N**, **D**, and **M** must be positive
numbers from 1 to 100 (**N** may also be zero). Here are some examples:

**1d20**
Roll the die with twenty sides once. This will result in a number from 1 to 20.

**3d6**
Roll the die with six sides three times adding the rolls together. This will
result in a number from 3 to 18.

**2d4-1**
Roll the die with four sides twice adding the rolls together, then subtract 1.
This will result in a number from 1 to 7.

It's possible to leave out parts of the specification. For example, if **N** is
omitted it defaults to 1. If **D** is omitted it defaults to 8. If **M** is
omitted it defaults to 0. The following are valid specifications:

**d20**
Roll the die with twenty sides once.

**2d**
Roll the die with eight sides twice adding the rolls together.

**1+1**
Roll the die with eight sides once, then add 1. That is, if **D** is omitted
then **d** can also be omitted.

**0+1**
Always results in the number 1.  The die, if specified, is unimportant.
For example, a blowgun always does 1 damage.

**d42**
Roll the die with 42 sides once. Probably not very useful for D&D.

## Advanced Dice Specification

In some cases we don't want all dice rolled to count.  For example, when rolling
ability scores, we roll 4d6 but keep only the top 3 dice.  Or when rolling
advantage or disadvantge, we roll d20 twice and keep the higher or lower die,
respectively.

To handle these cases, append the upper or lower modifier to a simple dice
specification.  Use **NdD+MuS** or **NdD+MlS** respectively, where **S** is
a positive number smaller than **N**.  **S** represents the subset
of dice that should count.

Here are some examples:

**4d6u3**
Roll the die with six sides four times, keeping only the three largest numbers.
Add the largest numbers together. This will result in a number from 3 to 18.

**2d20u1**
Roll the die with twenty sides twice, keeping only the higher value.  This
would be like rolling an ability check with advantage.

**2d20l1**
Roll the die with twenty sides twice, keeping only the lower value.  This
would be like rolling an ability check with disadvantage.

**S** can be left out if it's value is equal to **N-1**.  The following three
dice specifications are equivalent to the previous three, respectively:

**4d6u**
**2d20u**
**2d20l**

# Demos

See [demos of all the components](http://rogerta.github.io/dnd-dice/components/dnd-dice/demo/).
A much [fancier demo](http://dnd-tools.appspot.com/dice) also exists.

[Unit tests](http://rogerta.github.io/dnd-dice/components/dnd-dice/test/)

