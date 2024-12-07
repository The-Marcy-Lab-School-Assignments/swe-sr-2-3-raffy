# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

What are the main differences between Flexbox and Grid layouts? Describe scenarios where each layout system would be more suitable.

### Response 1
Generally, both **flexbox** and **grid** are useful in simplifying the process of creating responsive web layouts. Without the two, web developers will have to manually specify specific media-query breakpoints to account for resizing browser windows (or different device resolutions/sizes).

While you could achieve the same functionality/layout by using either **flexbox** or **grid**, a general rule of thumb is that if you don't have a specific layout in mind, styling using **flexboxes** is the way to go (for both simplicity and time to implement). **Grid** layouts are very powerful for when you want a responsive design but still retain some control in visual arrangement.

Your typical feed-type website like Instagram, or Twitter, where posts of that feed are of the same size and are orderly arranged can be solved using **flexboxes**. On the other hand, sites like Pinterest might urge you to use **grid** instead in order to create a dynamic layout of posts of different sizes.

## Prompt 2

What is the difference between `justify-content` and `align-items` in Flexbox? How does each property control the positioning of flex items within the container?

### Response 2
**Flexbox** items are arranged in terms of main and cross axis. What these axes mean may vary depending on the `flex-direction` property, but for this section, we will assume that it is set to the default of `flex-direction: row`.

An easy way to think approach the difference between the two is to "map" them like so:
- `justify-content` --> controls the behavior of child elements along the main axis

- `align-items` --> controls the behavior of child elements along the cross axis

```
            •
            |
            |
            |
•- - - - - - - - - - - -• main axis
            |
            |
            |
            •
        cross axis
```

Both of these properties have multiple possible values. To illustrate, let's take a look at both properties with values set to either (`flex-start`, `center`, and `flex-end`). Notice how `justify-content` values move the element along the **main axis**:
- `justify-content` set to `flex-start`
```
            •
 😭         |
            |
            |
•- - - - - - - - - - - -• 
            |
            |
            |          
            •
```

- `justify-content` set to `center`
```
            •
            🤨
            |
            |
•- - - - - - - - - - - -• 
            |
            |
            |          
            •
```

- `justify-content` set to `flex-end`
```
            •
            |          🥹
            |
            |
•- - - - - - - - - - - -• 
            |
            |
            |          
            •
```

Meanwhile `align-items` moves the element along the **cross axis**:
- `align-items` set to `flex-start`
```
            •
 😭         |
            |
            |
•- - - - - - - - - - - -• 
            |
            |
            |          
            •
```

- `align-items` set to `center`
```
            •
            | 
            |
            |
•🤨 - - - - - - - - - - -• 
            |
            |
            |          
            •
```

- `align-items` set to `flex-end`
```
            •
            |          
            |
            |
•- - - - - - - - - - - -• 
            |
            |
            |          
 🥹         •
```

To finish, you could also "mix" both properties!
- `justify-content` and `align-items` : both set to `center`
```
            •
            |          
            |
            |
•- - - - - -🙂‍↕️- - - - - -• 
            |
            |
            |          
            •
```

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3
`grid-template-areas` is an extension of CSS Grid, after having defined either or both `grid-template-columns` and `grid-template-rows` properties.

`grid-template-columns` and `grid-template-rows` are the two primary CSS properties that you start with when defining a grid structure. The former allows you to specify the width of individual columns, separated by a space.

```css
/* setting up a grid with two columns:
   the first column with a width of 50px
   the second column with a width of 1rem
*/
grid-template-columns: 50px 1rem;
```
![demo-1](/public/demo-1.png)

CSS also allows a neat shortcut for when you want to have a lot of columns that are of the same width.

```css
/* sets up a grid of 5 columns:
   1fr means that they all have the same width proportionate to each other
   and would occupy the full space of their container!
*/
grid-template-columns: repeat(5, 1fr);
```
![demo-2](/public/demo-2.png)

`grid-template-rows` serve the same purpose but for horizontal rows instead. Using both in conjuction with each other allows for a strict definition of a grid-pattern.

```css
/* sets up a 4x3 grid (4 rows, 3 columns)
   all of height and width of 2rem.
*/
grid-template-rows: repeat(4, 2rem);
grid-template-columns: repeat(3, 2rem);
```
![demo-3.png](/public/demo-3.png)

To add a layer of customization, grid then allows the use of `grid-template-columns` in order to create areas of varying sizes in a grid structure. Using the same template from above, here is an example of how you could define areas in CSS grid:

```css
/* sets up a 4x3 grid (4 rows, 3 columns)
   all of height and width of 2rem.
*/
grid-template-rows: repeat(4, 2rem);
grid-template-columns: repeat(3, 2rem);
/* splits up the 4x3 grid into 10 areas! */
grid-template-areas:
  "one one two"
  "three four four"
  "three four four"
  "six eight nine"
  "seven eight ten"
;
```
But that won't work right away. When using `grid-template-areas` you would also have to define an additional property for the children elements in order to match your defined areas above into them!
```css
/* assuming that you have divs whose id is 'item<number>' */
#item1 { grid-area: one; background-color: #a6cee3 }
#item2 { grid-area: two; background-color: #1f78b4 }
#item3 { grid-area: three; background-color: #b2df8a }
#item4 { grid-area: four; background-color: #33a02c }
#item5 { grid-area: five; background-color: #fb9a99 }
#item6 { grid-area: six; background-color: #e31a1c }
#item7 { grid-area: seven; background-color: #fdbf6f }
#item8 { grid-area: eight; background-color: #ff7f00 }
#item9 { grid-area: nine; background-color: #cab2d6 }
#item10 { grid-area: ten; background-color: #6a3d9a }
```
Then you get this custom grid with varying element sizes:
![demo-4.png](/public/demo-4.png)


## Prompt 4

Explain the `min-width` and `max-width` keywords in media queries. How do they help create responsive breakpoints for different screen sizes?

### Response 4
`min-width` and `max-width` both make it possible for CSS to detect and redefine itself depending on the viewport's size. Both of these properties act as thresholds which will detect and apply the changes defined inside of them whenever that condition is crossed. A `min-width` media query will apply the changes whenever the viewport is equal or more than the specified value, while `max-width` applies changes when the viewport is equal or less in size.

## Prompt 5

Imagine you are teaching a brief lesson on **mobile first design**. Your lesson should include the following information:

* An explanation of mobile first design and a few of the benefits of this approach
* A CSS code example demonstrating how to use media queries to adjust the layout of a container from mobile to desktop with either Flexbox or Grid (choose one).
* An explanation of the code example.

### Response 5


