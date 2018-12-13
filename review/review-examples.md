# Review examples

## Example 1
```html
<div class="header">
    <div id="logo">
        <img src="logo.jpg" alt="">
    </div>
    <div id="listElements">
        <ul>
        <a href="/about">About</a>
        <a href="/team">Team</a>
        <a href="/contact">Contact</a>
        <a href="/chalk-eaters-for-life">Why we eat chalk</a>
        </ul>
    </div>
</div>
```

Lets first get an overview of the code: We have a header with a logo and some links in a list. Now let’s start looking through the code. 

The first element is a div with a class of header. There is a header tag, so lets suggest to use that instead. `<header></header>`

Now there is a `div` with an id called logo. Using an id for a logo is okay, but be aware of not using id’s for styling! Id’s are used to indicate that an elements is truly unique. The logo div has an image child tag. But why? Depending on the case the wrapping div may not be necessary. So here we need to ask the developer if we really need the wrapping div. Otherwise remove it and just use the `img` tag. 
All images should have alt tags, so lets suggest to fill that in. 

Now we have another `div` with an id called `listElements`. Google recommends to seperate words with hyphen in html: https://google.github.io/styleguide/htmlcssguide.html#ID_and_Class_Name_Delimiters lets suggest that, so `listElements` becomes `list-elements`. But actually lets look at what this code does. It is a list of links in the header. That is called navigation links and there is a tag for that: `<nav></nav>` Lets suggest to use that instead. 

Now we have a `ul` and some link tags as its children. Firstly they need to be indented! When we have a `ul` its children should be `li` tags. That means that this html is not correct. So instead of having link tags as the children we need to wrap them in an `li` tag. 
```html
<ul>
    <li>
        <a></a>
    </li>
</ul>
```
So with the changes it should look like this:

```html
<header>
    <img id="logo" src="logo.jpg" alt="People eating chalk">
    <nav>
        <ul>
            <li><a href="/about">About</a></li>
            <li><a href="/team">Team</a></li>
            <li><a href="/contact">Contact</a></li>
            <li><a href="/chalk-eaters-for-life">Why we eat chalk</a></li>
        </ul>
    </nav>
</header>
```


## Example 2

```js
const arr1 = ['orange', 'eggs', 'apple', 'milk'];

function itemInArray(item) {
    var iteminarray = false;
    for (var i = 0; i < arr1.length; i++) {
        if(arr[i] === item) {
        itemInArray = true;
        }
    }

    return iteminarray;
}

console.log(iteminarray('milk'));
console.log(iteminarray('bread'));

```

First lets get an overview! We have an array with some items. We have a function being created and that function being called. The function is used for checking if an item is already in the array called arr1. 
Finding the point of entry is easy as the code starts from the top of the file. 

Firstly the `arr1` variable does not describe the content of the array. We already know it is an array, so this name `arr1` is not super good. Lets give a suggestion for a better name. It looks like the array contains products or foods. So i would call it products. `const products = …`
Now lets go into the function. First lets figure out what the function returns. It returns a variable that is a boolean. The `itemInArray` variable. When a function returns a boolean it can be helpful to indicate that, in the function name, so instead of `itemInArray`, lets call it `isItemInArray`. 

The first variable in the function is called `iteminarray`. In javascript best practice for variable naming is camelCase. So instead of calling it `iteminarray` lets suggest to change it to `itemInArray`. We are defining the variable using var, that is no go, lets suggest to use let instead.

Now a for loop is created to loop through all elements in the `arr1`. The function has access to `arr1` through the global scope. That means that the function is not self sufficient. It reaches out of its own scope. This should be avoided. Therefore lets suggest that the function takes another parameter called `arrayToSearch`. Instead of using `arr1` in the function we use `arrayToSearch`. 

Instead of using the for loop, lets suggest to use the `forEach` array function instead. So `arrayToSearch.forEach(() => {})`
On line 7 we set a variable called `itemInArray`. This is bad for two reasons. It is called the same as the function which could lead to confusion. The other reason is that the variable we are setting to true is actually the function! That means that every time an array is in the array we cannot use the function afterwards as the function is now a boolean! This should be changed.

Line 7 is not properly indented.

```js
const products = ['orange', 'eggs', 'apple', 'milk'];

function isItemInArray(item, arrayToSearch) {
    let itemInArray = false;
    arrayToSearch.forEach((searchingItem) => {
        if(searhingItem === item) {
            itemInArray = true;
        }
    });

    return itemInArray;
}

console.log(isItemInArray('milk'));
console.log(isItemInArray('bread'));
```


Okay now it looks like this. Better, but have we even used the right approach for solving this problem? There is an array method called `includes`, lets see what that does: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes 
The `includes` method determines whether an array includes a certain element, returning true or false as appropriate.
That is exactly what we need. Lets suggest to use that instead!


```js
const products = ['orange', 'eggs', 'apple', 'milk'];

function isItemInArray(item, arrayToSearch) {
    return arrayToSearch.includes(item);
}

const isItemInArrayArrowFunction = (item, arrayToSearch) => arrayToSearch.includes(item);

console.log(isItemInArray('milk'));
console.log(isItemInArray('bread'));
```

