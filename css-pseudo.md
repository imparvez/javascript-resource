# CSS Pseudo Selectors

They are nothing but CSS selectors with colon preceding them. 
Selects elements in certain conditions

##### Link Related Pseudo Selectors/Class
<hr>

For Eg: `a:hover`.

They are very helpful in variety of situations.

`:link` is same as `a`, just being specific. They both do the same thing.

`:active` is for when the user has clicked the element.

`:visited` is for when the user has visited the link before.

`:hover` is when the mouse cursor rolls over a link, that link is in it's hover state and this will select it.

##### Input & link related pseudo class selectors
<hr>

`:focus` will select the links that are current focus of the keyboard.

`:checked` is used to see if the checkboxes are checked or not.

##### Position/Number-based pseudo class selectors
<hr>

`:root` selects the topmost element in the document which is mostly `<html>`

`:first-child` selects the first child within the parent element

`:last-child` selects the last child within the parent element

`:nth-child()` selects the element based on simple provided algebraic expression.

`:first-of-type` selects the first element within the parent element

`:last-of-type` selects the last element within the parent element

`:only-of-type` selects only if the element is the <b>only one of its kind</b> within the current parent

