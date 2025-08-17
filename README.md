# JavaScript, BOM, and DOM Cheat Sheet

## Table of Contents
1. [JavaScript Basics](#javascript-basics)
2. [BOM (Browser Object Model)](#bom-browser-object-model)
3. [DOM (Document Object Model)](#dom-document-object-model)
4. [Common Web Page Manipulation Tasks](#common-web-page-manipulation-tasks)
5. [Event Handling](#event-handling)
6. [Useful Methods & Properties](#useful-methods--properties)
7. [Tips & Best Practices](#tips--best-practices)

---

## JavaScript Basics
- **Declare variable:** `let x = 5;`, `const y = 'hello';`, `var z = true;`
- **Function:** `function foo() { ... }`, `const bar = () => { ... }`
- **Console log:** `console.log('Message');`
- **Conditional:** `if (x > 0) { ... } else { ... }`
- **Loop:** `for (let i = 0; i < 10; i++) { ... }`

---

## BOM (Browser Object Model)
The BOM allows JS to interact with the browser (not the page content).

- **Window Object**
  - `window.alert('Hello!')` — Show alert box
  - `window.open('https://example.com')` — Open new tab/window
  - `window.close()` — Close current window
  - `window.innerWidth / innerHeight` — Viewport dimensions
  - `window.setTimeout(fn, ms)` — Run `fn` after delay
  - `window.setInterval(fn, ms)` — Run `fn` repeatedly

- **Navigator Object**
  - `navigator.userAgent` — Browser info
  - `navigator.language` — Language
  - `navigator.onLine` — Connection status

- **Location Object**
  - `location.href` — Get/set URL
  - `location.reload()` — Reload page
  - `location.assign(url)` — Navigate to URL
  - `location.replace(url)` — Replace current page

- **History Object**
  - `history.back()` — Go back
  - `history.forward()` — Go forward
  - `history.go(-1)` — Go n pages forward/back

- **Screen Object**
  - `screen.width / screen.height` — Screen size

---

## DOM (Document Object Model)
The DOM represents the page structure as a tree of objects.

- **Selecting Elements**
  - `document.getElementById('id')`
  - `document.getElementsByClassName('class')`
  - `document.getElementsByTagName('tag')`
  - `document.querySelector('selector')`
  - `document.querySelectorAll('selector')`

- **Manipulating Elements**
  - `element.innerHTML = 'Text'` — Set HTML
  - `element.textContent = 'Text'` — Set text
  - `element.style.color = 'red'` — Change style
  - `element.classList.add('class')` — Add class
  - `element.classList.remove('class')` — Remove class
  - `element.setAttribute('attr', 'value')` — Set attribute
  - `element.getAttribute('attr')` — Get attribute
  - `element.remove()` — Remove element

- **Creating/Adding Elements**
  - `let el = document.createElement('div')`
  - `parent.appendChild(el)`
  - `parent.insertBefore(newEl, refEl)`

---

## Common Web Page Manipulation Tasks
- **Change text:**
  ```js
  document.getElementById('id').textContent = 'New text';
  ```
- **Change style:**
  ```js
  document.querySelector('.myclass').style.backgroundColor = 'yellow';
  ```
- **Add element:**
  ```js
  let p = document.createElement('p');
  p.textContent = 'Hello!';
  document.body.appendChild(p);
  ```
- **Remove element:**
  ```js
  document.getElementById('id').remove();
  ```
- **Toggle class:**
  ```js
  element.classList.toggle('active');
  ```

---

## Event Handling
- **Add event listener:**
  ```js
  element.addEventListener('click', function(event) {
    // handle click
  });
  ```
- **Remove event listener:**
  ```js
  element.removeEventListener('click', handler);
  ```
- **Common events:**
  - `click`, `dblclick`, `mouseover`, `mouseout`, `keydown`, `keyup`, `submit`, `change`, `input`

---

## Useful Methods & Properties
- **Form values:**
  ```js
  document.querySelector('input').value
  ```
- **Check/Uncheck checkbox:**
  ```js
  checkbox.checked = true/false;
  ```
- **Scroll page:**
  ```js
  window.scrollTo(x, y);
  element.scrollIntoView();
  ```
- **Get parent/children:**
  ```js
  element.parentNode
  element.children
  ```
- **Get/Set custom data attribute:**
  ```js
  element.dataset.key = 'value';
  let val = element.dataset.key;
  ```

---

## Tips & Best Practices
- Always wait for DOM to load before manipulating:
  ```js
  document.addEventListener('DOMContentLoaded', function() {
    // your code here
  });
  ```
- Use `const` and `let` instead of `var`.
- Use `querySelector`/`querySelectorAll` for flexible selection.
- Minimize direct DOM manipulation for performance.
- Avoid using `innerHTML` with user input (XSS risk).
- Use event delegation for dynamic content:
  ```js
  document.body.addEventListener('click', function(e) {
    if (e.target.matches('.btn')) {
      // handle button click
    }
  });
  ```

---

**Keep this cheat sheet handy for quick reference!**
