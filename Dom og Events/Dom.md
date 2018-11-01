__1.DOM(3%).Lestu og gerðu eftirfarandi verkefni (e. tasks), sjá neðst í hverjum kafla.Document: https://javascript.info/document__
A.Walking the DOM: https://javascript.info/dom-navigation

 ```javascript
<html>
<body>
  <div>Users:</div>
  <ul>
    <li>John</li>
    <li>Pete</li>
  </ul>
</body>
</html>
 ```

How to access:
    The <div> DOM node?
    The <ul> DOM node?
    The second <li> (with Pete)?

There are many ways, for instance:
 
The <div> DOM node:
 
 ```javascript
document.body.firstElementChild
// or
document.body.children[0]
// or (the first node is space, so we take 2nd)
document.body.childNodes[1] //fyrsta barnið
 ```
The <ul> DOM node:
 
 ```javascript
document.body.lastElementChild
// or
document.body.children[1] //annað barnið
 ```
The second <li> (with Pete):
 
  ```javascript
// get <ul>, and then get its last element child //seinestabarnið
document.body.lastElementChild.lastElementChild
 ```
