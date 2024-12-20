## About the Project

This image carousel project was inspired by the <a href="https://www.theodinproject.com/lessons/node-path-javascript-dynamic-user-interface-interactions">"Dynamic User Interface Interactions"</a> section of the The Odin Project. 

## Lessons Learned
### Problem 1
In the curriculum, it is suggested to use a wide div as a container for the image slides. However, this approach presents a challenge: the images can only slide in one direction. When images are placed side by side within a large div, transitioning from image 1 to image 2 requires translating in the X direction by 100%. Upon reaching the final slide, clicking the right button would not be intuitive since it would require iterating through the intermediate slides to return to slide 1.

### Solution
I used temporary utility classes, such as .right-slide and .left-slide, which dynamically apply to the next HTML element when the user presses the left or right arrow button. This allows for smoother transitions between slides than a linear slide would create. Although other viable solutions would be to either:
<ol>
  <li>Quickly animate a transition that jumps to from the last slide back to the first</li>
  <li>Reset the position after the final slide is reached</li>
</ol>
I don't think it looks as asethetically pleasing...

### Problem 2
When a user presses one of the dot buttons below the carousel to jump between slides, the carousel needs to correctly identify the previous and next image elements relative to the current slide.

### Solution
I implemented a circular doubly linked list to represent the image elements. This structure allows the carousel to easily determine the previous and next image elements given the current slide. The final slide seamlessly circles back to the first slide.

Although in retrospect, I could've incremented and decremented the indices to find its sibling elements and created two "if" statements when reaching either ends of the NodeList of the "li" elements (containing the image element) to handle the exception... but this doesn't sound as cool as a circular doubly linked list

## Features
- Live previews
