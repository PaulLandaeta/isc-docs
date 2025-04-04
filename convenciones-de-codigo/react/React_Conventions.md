## ⚛️ **React Conventions**

**Referencia:** [Best Practices for React - FreeCodeCamp](https://www.freecodecamp.org/news/best-practices-for-react/)


## Componentes Funcionales
<p style="font-size: 16px;">React recomienda el uso de componentes funcionales en lugar de componentes de clase para una mejor legibilidad y rendimiento.</p>

```jsx
// ❌ Incorrect (Class-based component)
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

// ✅ Correct (Functional component)
const Welcome = ({ name }) => <h1>Hello, {name}!</h1>;
```

## Manejo de Estado
Para manejar el estado dentro de un componente, se recomienda el uso de `useState` en lugar de `this.state`.

```jsx
// ❌ Incorrect (Using class-based state)
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <button onClick={() => this.setState({ count: this.state.count + 1 })}>
        Count: {this.state.count}
      </button>
    );
  }
}

// ✅ Correct (Using useState)
import { useState } from "react";
const Counter = () => {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>Count: {count}</button>;
};
```

## Uso de Hooks
React proporciona hooks como `useEffect` y `useContext` para manejar efectos secundarios y contexto global.

```jsx
// ❌ Incorrect (Side effects inside component body)
const Component = () => {
  fetch("https://api.example.com/data").then((response) => response.json());
  return <div>Data Loaded</div>;
};

// ✅ Correct (Using useEffect)
import { useEffect, useState } from "react";
const Component = () => {
  const [data, setData] = useState(null);
  useEffect(() => {
    fetch("https://api.example.com/data")
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []);

  return <div>{data ? "Data Loaded" : "Loading..."}</div>;
};
```

## Manejo de Props

Los props deben ser utilizados de manera eficiente y evitar el uso innecesario de `prop drilling`.

```jsx
// ❌ Incorrect (Prop drilling)
const Child = ({ message }) => <h2>{message}</h2>;
const Parent = ({ message }) => <Child message={message} />;
const GrandParent = ({ message }) => <Parent message={message} />;

// ✅ Correct (Using Context API)
import { createContext, useContext } from "react";
const MessageContext = createContext();
const Child = () => {
  const message = useContext(MessageContext);
  return <h2>{message}</h2>;
};
const GrandParent = () => (
  <MessageContext.Provider value="Hello from Context!">
    <Child />
  </MessageContext.Provider>
);
```

## Buenas Prácticas Generales

✔ Utilizar `useState` y `useEffect` en lugar de métodos de ciclo de vida de clases.

✔ Evitar modificaciones directas del estado (`this.state = {...}`).

✔ Dividir componentes grandes en componentes reutilizables.

✔ Utilizar `React.memo` para optimizar rendimiento en componentes funcionales.

✔ Implementar `Error Boundaries` para manejar errores en la UI.

---

## Característica Única: **Error Boundaries**
<p style="font-size: 16px;">React permite capturar errores en la UI con `Error Boundaries` para evitar fallos inesperados en toda la aplicación.</p>

```jsx
// ✅ Correct (Using an Error Boundary)
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError() {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    console.log("Logging error:", error, info);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

```

---

Siguiendo estas mejores prácticas, el código en React será más **eficiente, mantenible y escalable**.
