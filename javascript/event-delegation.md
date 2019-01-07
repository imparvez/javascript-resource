# Event Delegation
- Event delegation in JavaScript lets you avoid adding event listeners to specific nodes; instead, the event listener is added to one parent.
- It analyzes the bubbled events to find a match on child elements.
- Example: Its basic principle is simple, when the event bubbles up to the UL element, 
  you check the event object's target property to gain a reference to the actual clicked node.
  
### Example no: 1
```html
<!-- Simple Example -->
<ul id="lists">
  <li id="item-1">1</li>
  <li id="item-2">2</li>
  <li id="item-3">3</li>
  <li id="item-4">4</li>
  <li id="item-5">5</li>
  <li id="item-6">6</li>
  <li id="item-7">7</li>
  <li id="item-8">8</li>
</ul>
```
```css
* {
  color: #fff;
}

ul {
  background-color: blue;
}

ul li {
  background-color: green;
  margin: 10px 15px;
  cursor: pointer;
}
```

```js
document.getElementById("lists").addEventListener("click", function(e){
  if(e.target && e.target.nodeName == "LI"){
    console.log("List Item: ", e.target.id.replace("item-", ""), " was clicked");
  } else {
    console.log("UL was clicked");
  }
})
```
---
### Example no: 2

```html
<div id="container">
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed dolor augue, lacinia eget eleifend imperdiet, viverra vel mauris. Suspendisse pharetra pulvinar nisi vel ornare. Phasellus quis lorem commodo, maximus quam in, laoreet purus. Sed venenatis a arcu sit amet rutrum. Suspendisse commodo suscipit eleifend. Nam eleifend diam vitae mauris efficitur, quis posuere leo luctus. Aliquam id auctor dolor. Nulla a magna hendrerit, condimentum odio eu, semper tellus. Integer in commodo nulla. Nam faucibus eu nulla at sagittis.</p>

  <a href="google.com">Google</a>

  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed dolor augue, lacinia eget eleifend imperdiet, viverra vel mauris. Suspendisse pharetra pulvinar nisi vel ornare. Phasellus quis lorem commodo, maximus quam in, laoreet purus. Sed venenatis a arcu sit amet rutrum. Suspendisse commodo suscipit eleifend. Nam eleifend diam vitae mauris efficitur, quis posuere leo luctus. Aliquam id auctor dolor. Nulla a magna hendrerit, condimentum odio eu, semper tellus. Integer in commodo nulla. Nam faucibus eu nulla at sagittis.</p>

  <a href="facebook.com">Facebook</a>

  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed dolor augue, lacinia eget eleifend imperdiet, viverra vel mauris. Suspendisse pharetra pulvinar nisi vel ornare. Phasellus quis lorem commodo, maximus quam in, laoreet purus. Sed venenatis a arcu sit amet rutrum. Suspendisse commodo suscipit eleifend. Nam eleifend diam vitae mauris efficitur, quis posuere leo luctus. Aliquam id auctor dolor. Nulla a magna hendrerit, condimentum odio eu, semper tellus. Integer in commodo nulla. Nam faucibus eu nulla at sagittis.</p>

  <a href="bookmyshow.com">BMS</a>

  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed dolor augue, lacinia eget eleifend imperdiet, viverra vel mauris. Suspendisse pharetra pulvinar nisi vel ornare. Phasellus quis lorem commodo, maximus quam in, laoreet purus. Sed venenatis a arcu sit amet rutrum. Suspendisse commodo suscipit eleifend. Nam eleifend diam vitae mauris efficitur, quis posuere leo luctus. Aliquam id auctor dolor. Nulla a magna hendrerit, condimentum odio eu, semper tellus. Integer in commodo nulla. Nam faucibus eu nulla at sagittis.</p>
</div>
```

```css
#container {
  background-color: maroon;
}
```

```js
document.getElementById("container").addEventListener("click", function(e){
    if(e.target && e.target.nodeName == "A"){
    console.log("anchor was clicked");
    e.preventDefault();
  }
})
```
---

# Event Bubbling/Propogation:

When a user makes a click on any event, it ripples up all
the way to the top of the DOM and triggers clicks events
on all parent elements of the element you clicked.
This means that anytime you click one of our inputs on the DOM
you are effectively clicking the entire document body.

### Example no: 1

```html
<!--Event Bubbling-->
<div class="one center">
  <div class="two center">
    <div class="three">

    </div>
  </div>
</div>
```
```css
.one {
  width: 500px;
  height: 500px;
  background-color: #c33;
}

.two {
  width: 350px;
  height: 350px;
  background-color: #ccc;
}

.three {
  width: 175px;
  height: 175px;
  background-color: #ff6;
}

.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

```js
const divs = document.querySelectorAll('div');

divs.forEach(div => div.addEventListener('click', logName));

function logName(event){
  console.log(this.classList.value)
}
```

As we click on `div#3`, I should see the class name of `div#3` being logged but instead I also see `div#2` and `div#1` being logged to the console. This is event bubbling.

This takes place because we added event listeners to each parent `div`
So on click of `div#3`, its parent `div#2` also have the click event on it, same goes for `div#1`

**Note:** To avoid this, we can place event listener on a single parent HTML element that lives above a HTML child, and that event listener will get executed whenever an event occurs on any of its child nodes - even if these node children are added to the page after the initial load.

### Conclusion:
- Without event delegation, we have to re-bind the click event listener to each new input loaded to the page. Coding this is complicated and burdensome.
- For one, it would drastically increase the amount of event listener on your page and more event listener would increase the total memory footprint of your page.
- This will result in performance decrement and poor performance.
---