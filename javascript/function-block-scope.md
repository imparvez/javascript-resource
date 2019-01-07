Three ways to create variables in javascript
- var
- const
- let

Whats unique about `var` is that you can re-assigned and update it as many times you want whereas you can't do the same for `const` and `let`.

`var` is function scope. This means they are only available inside the function they're created in, or if not created inside a function, they are globally scoped.

If `var` is defined inside a function and I subsequently try to call it outside the function, it won't work.

```js
function setWidth(){
	var width = 100;
	console.log(width);
}
setWidth(); // 100
console.log(width); // Uncaught ReferenceError: width is not defined
```

Again, `var` is defined inside a function and not available outside the function.

### Understanding Scope: