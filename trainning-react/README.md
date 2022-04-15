# =================== Day 2 ==================
# Excercise 2

1. What are React and React DOM? Why do you use React?
  - React is a Javascript library for building user interfaces
  - ReactDOM includes ReactDOMClient and ReactDOMServer
  ```
    react-dom package provides DOM-specific methods that can be used at the top level of your app and as an escape hatch to get outside the React model if you need to.
  ```

  ```
    react-dom/client package provides client-specific methods used for initializing an app on the client 
  ```

  ```
    reactDOMServer object enables you to render components to static markup. Typically, it’s used on a Node server
  ```

  -  Why do you use React? 
    ```
    React is excellent tool to create interactive Web/Mobile App
    Currently, React's popularity and have huge usage.

    React is easy to learn, have document clearly
    ```

2. Explain why we need transpiler (Babel) and bundler (Webpack) in our React projects?
  ```
    Babel: Make sure JS code is cross-browser compatible.It compiles newer JavaScript into older JavaScript.
    Webpack: Webpack is a tool to help you compile Javascript modules and can load static asset (img, css, ...)
  ```

3. Why listing need a key for each element? Why is it bad to use index for key? Give an example
  - Key help React identify which item has changed, give a unique identity for each element in list/array.
  ```
  React recommends that you do not use indexes as keys, since it could impact performance negatively and could lead to some unstable component behaviour.
  ```
  - Example: Have a list and render a item in table. Each rows have name item & input field. After render, fill the value on input field, and shuffe array & add key in each row is index of array.
  ```
    <button onClick={()=>shuffeArray()} title="shuffe"/>
    <Table>
        {list.map((item,index) => (
            <TableRow key={index}>
                <TableCell>{item.name}</TableCell>
                <TableCell>
                    <input/>
                </TableCell>
            </TableRow>
        ))}
    </Table>
  ```

4. What is your opinion about state? How can you design components to prevent lifting state up?
  - state is similar props, it private and fully controlled by component.
  - Branching UI follow state

5. What is state batch updating?
  - Update many state in once rendering

6. What is higher order component pattern?
  - HOC pattern is made for reusing component logic. HOC component is func that take a component and return new component  
7. What is render prop pattern?
    - Render props is a props of component which value is a function that return JSX element. Render props pattern can make component reusable 
    ```
    Link reference: https://www.patterns.dev/posts/render-props-pattern/
    ```
8. Differences between HOC and hook? Which one you prefer and why
    - Hook: Can reuse stateful logic without change component hirarchy
    - HOC: Restructure compoent when using, difficult to read
    - Prefer using Hook: Beacause Hook is readability, highly reuseable, can separate logic and rendering and have good performance (less re-render)
9. Differences between controlled and uncontrolled components?
  - Controlled components: value was controlled by component
  - Uncontrolled Components: the value was proccessed by DOM (eg: submit form), React doesn't do any action when a change occurs
