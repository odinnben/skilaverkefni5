Events(3%).Lestu og gerðu eftirfarandi verkefni (e.tasks), 
sjá neðst í hverjum kafla.Introduction into Events: https://javascript.info/documentEvents in details:  
https://javascript.info/event-details

a.Browser events: https://javascript.info/introduction-browser-events

Create a function runOnKeys(func, code1, code2, ... code_n) that runs func on simultaneous pressing of keys with codes code1, code2, …, code_n.

For instance, the code below shows alert when "Q" and "W" are pressed together (in any language, with or without CapsLock)

```javascript
runOnKeys(
  () => alert("Hello!"),
  "KeyQ",
  "KeyW"
);
```

Lausn:


```javascript
<!DOCTYPE HTML>
<html>
<body>

  <p>Press "Q" and "W" together (can be in any language).</p>

  <script>
    function runOnKeys(func, ...codes) {
      let pressed = new Set();

      document.addEventListener('keydown', function(event) {//Þegar þú ert að ýtas á 
        pressed.add(event.code);

        for (let code of codes) { // are all keys in the set?
          if (!pressed.has(code)) {
            return;
          }
        }

        // yes, they are

        // during the alert, if the visitor releases the keys,
        // JavaScript does not get the "keyup" event
        // and pressed set will keep assuming that the key is pressed
        // so, to evade "sticky" keys, we reset the status
        // if the user wants to run the hotkey again - let them press all keys again
        pressed.clear();

        func();
      });

      document.addEventListener('keyup', function(event) {//keyup þegar þu ert að sleppa keyinum 
        pressed.delete(event.code);
      });

    }

    runOnKeys(
      () => alert("Hello!"),//ef er ýtt á q og w poppar alert gluggi 
      "KeyQ",
      "KeyW"
    );
  </script>

</body>

</html>

```

