```tsx
// 🖥️ TypeScript (TSX) Quick Guide 🚀

import React, { useState, useEffect } from "react";

// 🎨 Basic Component
const HelloWorld: React.FC = () => {
  return <h1>Hello, World! 🌍</h1>;
};

// 🎭 Props in Components
interface GreetingProps {
  name: string;
}
const Greeting: React.FC<GreetingProps> = ({ name }) => {
  return <h2>Hello, {name}! 👋</h2>;
};

// 🔀 State Management
const Counter: React.FC = () => {
  const [count, setCount] = useState<number>(0);

  return (
    <div>
      <p>Count: {count} 🔢</p>
      <button onClick={() => setCount(count + 1)}>➕ Increment</button>
      <button onClick={() => setCount(count - 1)}>➖ Decrement</button>
    </div>
  );
};

// ⏳ useEffect Hook
const Timer: React.FC = () => {
  const [seconds, setSeconds] = useState<number>(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds((s) => s + 1);
    }, 1000);

    return () => clearInterval(interval); // 🛑 Cleanup function
  }, []);

  return <p>⏳ Timer: {seconds} seconds</p>;
};

// 🎯 Event Handling
const ClickButton: React.FC = () => {
  const handleClick = (event: React.MouseEvent<HTMLButtonElement>) => {
    alert("Button Clicked! 🎉");
  };

  return <button onClick={handleClick}>Click Me! 🖱️</button>;
};

// 🔍 Conditional Rendering
const StatusMessage: React.FC<{ isOnline: boolean }> = ({ isOnline }) => {
  return <p>{isOnline ? "🟢 Online" : "🔴 Offline"}</p>;
};

// 🔗 Mapping Over Arrays
const List: React.FC<{ items: string[] }> = ({ items }) => {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>📌 {item}</li>
      ))}
    </ul>
  );
};

// 🌐 Fetch API (useEffect Example)
const FetchData: React.FC = () => {
  const [data, setData] = useState<string[]>([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then((res) => res.json())
      .then((json) => setData(json.map((post: any) => post.title)));
  }, []);

  return <List items={data} />;
};

// 🏗️ Context API
interface ThemeContextType {
  theme: string;
  toggleTheme: () => void;
}
const ThemeContext = React.createContext<ThemeContextType | null>(null);

const ThemeProvider: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const [theme, setTheme] = useState("light");

  const toggleTheme = () => setTheme(theme === "light" ? "dark" : "light");

  return <ThemeContext.Provider value={{ theme, toggleTheme }}>{children}</ThemeContext.Provider>;
};

const ThemeSwitcher: React.FC = () => {
  const context = React.useContext(ThemeContext);
  if (!context) return null;

  return <button onClick={context.toggleTheme}>Toggle Theme 🎨</button>;
};

// 🎉 Combining Components
const App: React.FC = () => {
  return (
    <ThemeProvider>
      <div>
        <HelloWorld />
        <Greeting name="Alice" />
        <Counter />
        <Timer />
        <ClickButton />
        <StatusMessage isOnline={true} />
        <FetchData />
        <ThemeSwitcher />
      </div>
    </ThemeProvider>
  );
};

export default App;
```
