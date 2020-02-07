---
tags: [Javascript /7. The DOM]
title: Document Object Model (10.4)
created: '2019-12-22T23:19:49.387Z'
modified: '2019-12-23T00:01:39.568Z'
---

# Document Object Model (10.4)

Consider a button
### Properties 
button.property
* innerHTML
* style
* firstChild

### Methods
button.method()
* click()
* appendChild()
* setAttribute()

## Selecting HTML elements with JS 
Gets all elements with tag name "li" in an array
`document.getElementsByTagName("li")`

to make 3rd element a purple color:
`document.getElementsByTagName("li")[2].style.color = "purple";`

To get the HTML line:
`document.querySelector(".btn");`
