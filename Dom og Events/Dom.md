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

Lausn:


There are many ways, for instance:
 
The <div> DOM node:
 
 ```javascript
document.body.firstElementChild // fyrsta barnið af <body> sem er sibling af <hrml>
// or
document.body.children[0] // sama conpent og efra
// or (the first node is space, so we take 2nd)
document.body.childNodes[1] 
 ```
The <ul> DOM node:
 
 ```javascript
document.body.lastElementChild // seiinasta barnið af <body> sem er sibling af <html>
// or
document.body.children[1] // sama conbpet af efra en þarna er [1] þvi af efri myndi vera [0] og ef eg væri með tildæmis <h1>  þá væri það document.body.childnodes[2]
 ```
The second <li> (with Pete):
 
  ```javascript
// get <ul>, and then get its last element child //seinestabarnið
document.body.lastElementChild.lastElementChild // seinasta barnið af <UL> 

ef eg væri að ná í Jhon þa væri það document.body.lastelemt.child.firstelementchild þvi að hann er fyrst barnið af <UL>
 ```
