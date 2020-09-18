### Remember

Answer these on your own, then compare answers as a group

1.  What is React?
React is a Javascript library/framework that is used to create interactive UIs

2.  What is create-react-app?
create-react-app is a script that creates some simple react boilerplate allowing devs to get started on a project quickly.

3.  What is Component Based Architecture?
Component-based architecture can be considered a design philosophy that emphasizes seperating blocks of code into modular, reusable components.

4.  What is JSX?
JSX, also known as Javascript XML allows us to write HTML alongside our React/Javascript code

5.  What is the virtual DOM?
The virtual DOM is sort of a copy or representation of the real DOM, which React compares against the real DOM to make changes.

6.  What is unidirectional (one-way) data flow?
Unidirectional data flow in react means that data only flows in one direction.  In React, this is downwards.  

### Understand

Discuss these questions in pairs if you have a 4-person group

7.  Summarize what happens when you run `create-react-app my-app`
Running this command in terminal will create a folder called my-app, and then create a react application boilerplate by installing all the needed dependencies (such as react, reactdom, etc) and setting up some configuartion.

8.  Explain what this code does:
Displays "lead" next to Time Biles 

```jsx
import React from "react";

const Mentor = props => (
  <div className="mentor-container">
    <h1 className={props.title === "Lead Mentor" ? "lead" : ""}>Tim Biles</h1>
    <ul>
      <li>Fort Worth, TX</li>
      <li>My email address is timbilestimbiles@gmail.com</li>
    </ul>
  </div>
);

export default Mentor;
```

9.  Explain how data is passed from a parent component to a child component.
Using props, you can pass data from a parent component to a child component 

### Apply

Try these on your own, but work together if you start to get stuck.

10.  Use `create-react-app` to create a new React application called `student-directory`

11.  Use the code from `Mentor` above to create a new functional, stateless component called `User` with a list of friends. Hard code the list of friends, do not use state or props.

### Analyze, Evaluate, Create

Discuss these questions as a group

12. What are the benefits and drawbacks of using a tool like create-react-app?

13. Compare and contrast JSX with other templating options, such as those used in Angular or Vue

14. Compare and contrast one-way data flow with two-way data binding.
