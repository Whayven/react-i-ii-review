### Remember

Answer these on your own, then compare answers as a group

1.  What are props?
- Props are data that's passed from a parent component to a child component 

2.  How do you pass props from a parent to a child?
- You pass props as actual properties on the child component tag. You pass the name of the prop as the key (left), and the data you want to pass as the value (right). 

3.  How do you access props from a class based child component?
- You can access props from a class based child component by accessing the props object (this.props.property)

4.  How do you access props from a functional component?
- Similarly to class components, you must access the props object, however you must recieve the prop object as a parameter in the functional component, and you can access the prop object directly, without "this"

5.  How do you bind a function to a parent component so that it can be passed to a child?
- You can bind functions to a parent components context in the constructor of the parent component
- this.functionName = this.functionName.bind(this)

### Understand

Discuss this question in pairs if you have a 4-person group

6.  What's happening in this component?
- Questions are stored in the Queue's state
- Queue has a function to add a question to an array in its state
- Queue has a function to remove a question at a specified index from an array in its state
- These functions are bound to Queue's context
- Queue passes these functions to its child components, Student and Mentor.
- When Student or Mentor access these functions through props, since it is bound to Queue, it will still affect the array in Queue's state, questions

```jsx
import React, { Component } from "react";

class Queue extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questions: []
    };

    this.askQuestion = this.askQuestion.bind(this);
    this.answerQuestion = this.answerQuestion.bind(this);
  }
  askQuestion(newQuestion) {
    const questions = [...this.state.questions, newQuestion];
    this.setState({ questions });
  }
  answerQuestion(index) {
    const questions = [...this.state.questions];
    questions.splice(index, 1);
    this.setState({ questions });
  }
  render() {
    <div className="queue-container">
      <h1>The Queue</h1>
      <h3>{this.state.questions.length}</h3>
      <h3>questions need answers</h3>
      <Student askQuestion={this.askQuestion} />
      <Mentor answerQuestion={this.answerQuestion} />
    </div>;
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

7.  Using the `Queue` component above, create a `Student` component that can add a question as a string and a `Mentor` component that can remove a question from the array.

### Analyze, Evaluate, Create

Discuss these questions as a group

8.  In the Queue component above, why are we holding state in the Queue component instead of Mentor or Student?
