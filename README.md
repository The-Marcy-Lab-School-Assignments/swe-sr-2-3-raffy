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
> `justify-content` --> controls the behavior of child elements along the main axis
> `align-items` --> controls the behavior of child elements along the cross axis

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

Both of these properties have multiple possible values, and to illustrate a combination of three simple values (`flex-start`, `center`, and `flex-end`) implemented in both axes:

`justify-content: flex-start` and `align-items: center`
```
            •
            |
            |
            |
•😭 - - - - - - - - - - -• 
            |
            |
            |          
            •
```

`justify-content: center` and `align-items: flex-end`
```
            •
            |
            |
            |
•- - - - - - - - - - - -• 
            |
            |
            🤨          
            •
```

`justify-content: flex-end` and `align-items: flex-start`
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

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3


## Prompt 4

Explain the `min-width` and `max-width` keywords in media queries. How do they help create responsive breakpoints for different screen sizes?

### Response 4

## Prompt 5

Imagine you are teaching a brief lesson on **mobile first design**. Your lesson should include the following information:

* An explanation of mobile first design and a few of the benefits of this approach
* A CSS code example demonstrating how to use media queries to adjust the layout of a container from mobile to desktop with either Flexbox or Grid (choose one).
* An explanation of the code example.

### Response 5

