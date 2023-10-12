// Exercise https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/A_first_splash
****Definition of the DOM and Basic concepts****

The DOM stands for Document Object Model. It can simply be understood as a tree of nodes created by the browser
We have 4 major ways of selecting elements:
- `document.getElementById('master')` -> find the element.
- `document.getElementsByClassName("master2")` -> returns a collection of all elements in the document with the specified class name
- `document.getElementsByTagName('p')` -> returns all the elements of the specified tag name in the order which they appear in the document
- `document.querySelector("#master")` -> returns the first value that matches the selector it’s given
- `document.querySelectorAll(".master")` -> a node list collection of all matching elements

With the HTML DOM, you can navigate the node tree and access nodes in the tree using node relationships we talked about earlier

    1) Every node has exactly one parent, except the top node (which has no parent).
    2) A node can have a more than one child.
    3) Siblings (brothers or sisters) are nodes with the same parent.
We can have the following node properties:

- parentNode
- childrenNodes
- firstElementChild
- lastElementChild
- nextElementSibling
- previousElementSibling

****How to Manipulate Elements in the DOM****
-  create elements


    const createEl = document.createElement('div') 


-  set the innerHTML/ text content of an element


    const innerhtml = createEl.innerHTML = 'i am a frontend developer'

-  append an element


    const parentEl = document.getElementById('parent')
    parentEl.appendChild(createEl) // It can append only Node objects to the parent element
    parentEl.append(createEl) // append() - It appends the Node objects or DOMString object to the parent element.

-  insert one element before another


    const firstchildEl = document.getElementById('firstchild')
    parentEl.insertBefore(createEl, firstchildEl)
    parentEl.replaceChild(createEl, firstchildEl)


-  replace a child element


    parentEl.replaceChild(createEl, firstchildEl)


-  remove a child element


    parentEl.removeChild(firstchildEl)

-  Add/Remove a CSS Class

    
    <style>
        .button{
            background-color: blueviolet;
        }
    </style>
    <button id="master">Click me</button>
    const buttonEl = document.getElementById('master')
    buttonEl.addEventListener('click', myFunction)
    function myFunction(){
        buttonEl.classList.add('button')
        buttonEl.classList.remove('button')
        buttonEl.classList.toggle('button') //remove CSS style completely
    }

![dom_manipulation.png](images%2Fdom_manipulation.png)