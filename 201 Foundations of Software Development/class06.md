## Problem Domain, Objects, and the DOM

to help solve the problem domain fully understand the question being asked and ask what and what question. By doing this you will have an easier time coding when you know the specific  details of the problem

Primitive values and object references are stored in JavaScript programs in different ways.

primitive valus are stored directly like `let classIn = 201`
while object references store let a varible store an object like
`let moe = {
  name: 'Moe Szyslak',
  occupation: 'Bartender',
  voicedBy: 'Hank Azaria'
};`

## chapter 3

you can add function to your objects
`let moe = {
  name: 'Moe Szyslak',
  occupation: 'Bartender',
  voicedBy: 'Hank Azaria'
  getGreeting: {
    return "my name is" + this.name; 
  }
};`
And you have to call the function using the objest name
`moe.getGreetings ();`

## chapter 5

`document.getElementbyid()` selects the html by its id to then edid using javascript.
`.textContent()` or `.innerHtml()` allow you to edit or add to an element.
an element is called a child when  its nestesd insided another elements making that its parent.




[table of content](./README.md)