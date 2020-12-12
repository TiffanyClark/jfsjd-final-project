# Task 4: Adding Items(posts or products)

## Description

For this task, we'll be creating a class to manage the items(products or posts), adding a method to the class to keep track of items in our application, and connecting up the New Item form to create items(products or posts).

## Walkthrough

### Step 1: The Setup

In this step, we'll re-organise our folder structure in preparation for the next few steps.

1. Create a `js` folder in your project if one does not already exist
2. Copy the existing js file into your `js` folder, and rename it to `index.js`
3. Update the `<script>` tag in your `html` file to use the new location of the `js/index.js` file.
4.  Create a `itemsController.js` file in the `js` folder
5. Add a `<script>` tag pointing to the `js/itemsController.js` file _before_ the `<script>` tag pointing to the `js/index.js` file.

### Step 2: The ItemsController Class

In this step, we'll create a `ItemsController` class that 
will be responsible for managing the items(posts or products) in the application. Always aim to use meaningful and long names to make your code more readable. We encourage you to replace the word `Items` with a more meaninfull one depending on your project domian:
* PostsController
* ProductsController

> #### Useful Resources for this step
> - [ECMAScript 2015 Classes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#ECMAScript_2015_Classes)

1. Create a `ItemsController` class in `js/itemsController.js`
2. Within the `constructor` of the `ItemsController` class, initialize a `this.items` property on the class equal to an empty array.

> #### Test Your Code!
> Now is a good chance to test your code, head over to `js/itemsController.js` and do the following
>
> 1. Initialize a new instance of `ItemsController`
> 2. `console.log()` the `items` property
>
> **Expected Result**
> You should see an empty array logged to the browser.

### Step 3: Adding A New Item Programmatically

In this step, we'll add a method to the `ItemsController` class that will allow us to add new items to array.

As part of this process, we're going to create a unique `id` for each item.

For each item to have a unique `id`, we will need to keep track of what `id` the latest task was created with, so that we can increment that `id` for the next item.

For example, pay attention to the two `items` objects below:
```js

//E-commerce project
const product1 = {
    id: 1,
    name: ''Tayto'',
    description: 'Cheese & Onion Chips',
    img: 'https://www.irishtimes.com/polopoly_fs/1.4078148!/image/image.jpg'
    createdAt: '2020-09-20'
};

const product2 = {
    id: 2,
    name: ''Water'',
    description: 'Mineral water',
    img: 'http://www.mazalv.com/wp-content/uploads/2016/11/Bottled-Water1-979x1024-1-979x1024.png'
    createdAt: '2020-09-20'
};


//Social Media project
const post1 = {
    id: 1,
    name: 'My first post',
    text: 'This is my first post',
    img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/Post-greenland-uummannaq.jpg/1200px-Post-greenland-uummannaq.jpg"
    author: 'Andres Lowles',
    createdAt: '2020-09-20'
};

const post2 = {
    id: 2,
    name: 'My second post',
    text: 'This is my second post',
    img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/Post-greenland-uummannaq.jpg/1200px-Post-greenland-uummannaq.jpg"
    author: 'Andres Lowles',
    createdAt: '2020-09-20'
};
```

Notice how each item has a unique `id`? We will be using this `id` in future steps to keep track of the different items. 

> #### Useful Resources for this step
> - [Array.prototype.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

1. In the `ItemsController`'s `constructor`, accept a `currentId` parameter, with a default value of `0`.
2. Assign the `currentId` to a new property on the class, `this.currentId`.
3. Create a method on the class, `addItem`. This method should accept all the nessecary information from the form to create an item as parameters.
    * Product
    - `name`
    - `description`
    - `img`
    - `createdAt`
    * Post
    - `name`
    - `text`
    - `img`
    - `author`
    - `createdAt`
 
4. Within the `addItem` method, increment the `this.currentId`
5. `push` a new item into the `this.items` array, with the correct properties of the item, using the values passed in as parameters as well as the new `this.currentId`
    **Note** Make sure to include the `id`

> #### Test Your Code!
> Now is a good chance to test your code, head over to `js/itemsController.js` and do the following
>
> 1. Initialize a new instance of `ItemsController`
> 2. Use the `addItem` method to add a new item
> 2. `console.log()` the `items` property
>
> **Expected Result**
> You should see an array containing the added item logged to the browser.

### Step 4: Adding Items With The Form

In this final step, we will use the `ItemsController` class to keep track of items we add with the **New Item** form.

**Note**: For now, if your **New Item** form is on a seperate page to your **Items List**, copy it over to your **Items List** so it's all on the one page.

> #### Useful Resources for this step
> - [Document.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
> - [EventTarget.addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
> - [Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)

1. Make sure a new `ItemsController` is initialized near the top of the file.
2. In `index.js`, add an event listener to the **New Item** form, listening to the `submit` event. If there is already an event listener used for validation, use that one.
3. When the `submit` event fires, if validation of the form is successful, use the values of each `input` in the form to call the `itemsController`'s `addItem` method.
    - **Note**: Make sure to prevent the default action of the form!
4. Clear the values from each form input, ready for the next submission.

## Results

We've now set up the `ItemsController` class, created an `addItem` and hooked it up to our **New Item** form!

Test out your code by adding some items using the **New Item** form, and checking the `ItemsController` instance's `items` array for the tasks.

## Example

Stuck? Check out the provided example in the [example/](example/) folder!