REACT COURSE
================
JSX
---

JSX is an XML-like syntax extension to ECMAScript without any defined semantics. It's NOT intended to be implemented by engines or browsers. It's NOT a proposal to incorporate JSX into the ECMAScript spec itself. It's intended to be used by various preprocessors (transpilers) to transform these tokens into standard ECMAScript.

---
html
```html
<div>Hello</div>
```
jsx
```javascript
React.createElement(
  "div",
  null,
  "Hello"
);
```
---

html
```html
var nav = (
    <ul id="nav">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Clients</a></li>
      <li><a href="#">Contact Us</a></li>
    </ul>
);
```
jsx
```javascript
var nav = React.createElement(
   "ul",
   { id: "nav" },
   React.createElement(
      "li",
      null,
      React.createElement(
         "a",
         { href: "#" },
         "Home"
      )
   ),
   React.createElement(
      "li",
      null,
      React.createElement(
         "a",
         { href: "#" },
         "About"
      )
   ),
   React.createElement(
      "li",
      null,
      React.createElement(
         "a",
         { href: "#" },
         "Clients"
      )
   ),
   React.createElement(
      "li",
      null,
      React.createElement(
         "a",
         { href: "#" },
         "Contact Us"
      )
   )
);
```
---

REACT
===========
---
Esempio di visualizzazione messaggio in React
```html
<!DOCTYPE html>
<html>
    <head>
        <script src="https://fb.me/react-15.2.0.js"></script>
        <script src="https://fb.me/react-dom-15.2.0.js"></script>
    </head>
<body>
    <div id="app"></div>
    <script>
        var HelloMessage = React.createClass({
            displayName: 'HelloMessage',
            render: function render() {
                return React.createElement('div',null,'Hello ',this.props.name);
            }
        });
        ReactDOM.render(React.createElement(HelloMessage,{ name: 'John' }), document.getElementById('app'));
    </script>
</body>
</html>
```
---

OUTPUT
Hello John

---

Using JSX via Babel

---

```html
<!DOCTYPE html>
<html>
    <head>
        <script src="https://fb.me/react-15.2.0.js"></script>
        <script src="https://fb.me/react-dom-15.2.0.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
    </head>
<body>
    <div id="app"></div>
    <script type="text/babel">
        var HelloMessage = React.createClass({
            render: function() {
                return <div>Hello {this.props.name}</div>;
            }
        });

        ReactDOM.render(<HelloMessage name="John" />, document.getElementById('app'));
    </script>
</body>
</html>
```

---

Using ES6 with React Component

```html
<!DOCTYPE html>
<html>
    <head>
        <script src="https://fb.me/react-15.2.0.js"></script>
        <script src="https://fb.me/react-dom-15.2.0.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
    </head>
<body>
    <div id="app"></div>
    <script type="text/babel">

        class HelloMessage extends React.Component { //notice use of React.Component
            render(){
                return <div>Hello {this.props.name}</div>;
            }
        };

        ReactDOM.render(<HelloMessage name="John" />, document.getElementById('app'));

        /*** PREVIOUSLY ***/
        /* var HelloMessage = React.createClass({
         *    render: function() {
         *        return <div>Hello {this.props.name}</div>;
         *    }
         * });
         *
         * ReactDOM.render(<HelloMessage name="John" />, document.getElementById('app'));
         */
    </script>
</body>
</html>
```

---

What Is a React Node?

<p><em>a light, stateless, immutable, virtual representation of a DOM node.</em></p>
<p>Non sono rappresentazioni reali dei nodi del DOM, bensí una rappresentazione di potenziali nodi del DOM</p>

---