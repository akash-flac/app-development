## Why braces in props of components?

### **What Are Props?**

In React and React Native, **props** (short for properties) are how data is passed from a parent component to a child component. They are essentially the "parameters" of a React component.

---

### **When to Use Curly Braces in Props**

1. **For Non-String Values**:
    
    - Props that take **numbers**, **booleans**, **arrays**, **objects**, or **expressions** must use curly braces `{}`.
    
    Examples:
    
    ```jsx
    // Number
    keyboardVerticalOffset={20}
    
    // Boolean
    showsVerticalScrollIndicator={false}
    
    // Object
    style={{ flex: 1 }}
    
    // Expression (function or variable)
    onPress={() => alert('Button clicked!')}
    data={myArray}
    ```
    
2. **For Strings**:
    
    - Strings can be written directly without curly braces.
    
    Examples:
    
    ```jsx
    // Correct
    placeholder="Enter your name"
    
    // Also correct (though less common for strings)
    placeholder={"Enter your name"}
    ```
    
3. **For Props Without Values (Boolean Props)**:
    
    - If a prop is `true` by default, you can omit the value altogether.
    
    Examples:
    
    ```jsx
    // Both mean the same (default is true)
    autoCorrect
    autoCorrect={true}
    ```
    

---

### **Why the Curly Braces?**

Curly braces in JSX allow you to embed **JavaScript expressions** inside the markup. Without curly braces, React treats the value as a literal string.

#### Example:

```jsx
<Button title="Click Me" color="blue" onPress={() => console.log('Pressed!')} />
```

- `title="Click Me"` is a string and doesn't need curly braces.
- `color="blue"` is also a string.
- `onPress={() => console.log('Pressed!')}` is a JavaScript function, so it requires curly braces.

---

### **Summary of Syntax Rules**

|**Prop Type**|**Syntax**|**Example**|
|---|---|---|
|**String**|Use quotes (`"`)|`title="Click Me"`|
|**Number**|Use curly braces (`{}`)|`keyboardVerticalOffset={20}`|
|**Boolean**|Use curly braces or omit|`autoCorrect` or `autoCorrect={true}`|
|**Object**|Use curly braces (`{}`)|`style={{ flex: 1 }}`|
|**Function**|Use curly braces (`{}`)|`onPress={() => alert('Hi')}`|
|**Expression**|Use curly braces (`{}`)|`value={count + 1}`|

---

Let me know if you'd like to dive deeper into specific examples!
## Why 2 curly braces in inline styling?

The double curly braces in `style={{ flex: 1 }}` are used because of how JSX handles inline styles in React and React Native. Let me break it down:

---

### **First Curly Brace: JSX Expression**

The **outer pair of curly braces** is for embedding a JavaScript expression inside JSX. This is the standard syntax for any prop value that is not a simple string.

Example:

```jsx
<View style={/* JavaScript Expression */} />
```

---

### **Second Curly Brace: JavaScript Object**

The **inner pair of curly braces** represents a JavaScript object. In React Native, the `style` prop expects an object to define styles (similar to CSS rules but written as a JavaScript object).

Example:

```jsx
style={{ flex: 1 }}
```

Here:

- The outer curly braces embed the JavaScript expression.
- The inner curly braces create the style object: `{ flex: 1 }`.

---

### **Why Two Curly Braces?**

You're effectively writing:

```jsx
style={ { flex: 1 } }
```

1. **Outer `{}`**: Tells JSX you're passing a JavaScript expression.
2. **Inner `{}`**: Defines the actual object (e.g., `{ flex: 1 }`).

---

### Example Without Confusion

Consider:

```jsx
<Text style={{ color: 'blue', fontSize: 20 }}>Hello, world!</Text>
```

- The `style` prop is being passed an object `{ color: 'blue', fontSize: 20 }`.
- The outer `{}` is JSX syntax.
- The inner `{}` is the JavaScript object.

---

### **What If You Use a Variable?**

You can avoid double braces by defining the style object in a variable:

```jsx
const styles = {
  container: {
    flex: 1,
    backgroundColor: 'lightblue',
  },
};

<View style={styles.container} />
```

Here:

- `styles.container` is already a JavaScript object.
- Only one set of curly braces is needed: `style={styles.container}`.

---

### Key Takeaway:

Double curly braces occur because:

1. JSX requires curly braces to embed JavaScript.
2. The `style` prop expects a JavaScript object.

## 