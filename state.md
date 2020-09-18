### Remember

Answer these on your own, then compare answers as a group

1.  What is state?

- State is an object that contains property values for your component
- The state object is available within class components, but not functional components 

2.  Where do you set initial state?

- In the constructor after we invoke super, this.state = {}

3.  What method do you use to update state?

- this.setState({ property: newValue })

### Understand

Discuss this question in pairs if you have a 4-person group

4.  Explain what's happening in this component.

- questionsAnswered is initialized at 0
- Everytime the button is clicked, button calls its onClick (handleClick)
- The onClick increases questionsAnswered by 1
- This data is presented as something like "Tim Biles" followed by the value of questionsAnswered, followed by the button increase that value by one each time it is pressed

```jsx
import React, { Component } from "react";

class LeadMentor extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: 0,
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAnswered: this.state.questionsAnswered + 1 });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Tim Biles</h1>
      <h3>{this.state.questionsAnswered}</h3>
      <h3>questions answered today</h3>
      <button onClick={this.handleClick}>Increase Answers</button>
    </div>;
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Create a `Student` component that keeps track of the number of questions the student has asked, with a button that adds 1 to the total when it's clicked

```jsx
import React, { Component } from "react";

export default class Student extends Component {
  constructor() {
    super();

    this.state = {
      questionsAsked: 0,
    };

    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState({ questionsAsked: questionsAsked + 1 });
  }

  render() {
    return (
      <div>
        <h1>Wayne Foster</h1>
        {this.state.questionsAsked + " "} questions asked today.
        <button onClick={this.handleClick}>Ask Question</button>
      </div>
    );
  }
}
```

6.  Now add a text input where the student can type in their questions with a button to add them to a list of questions that is displayed below the number of questions asked.

```jsx
import React, { Component } from "react";

export default class Student extends Component {
  constructor() {
    super();

    this.state = {
      questionsAsked: 0,
      questions: [],
      input: ''
    };

    this.askQuestion = this.askQuestion.bind(this);
    this.handleInput = this.handleInput.bind(this);
    this.addQuestion = this.addQuestion.bind(this);
  }

  askQuestion() {
    this.setState({ questionsAsked: questionsAsked + 1 });
  }

  handleInput(val) {
    this.setState({ input: val });
  }

  addQuestion() {
    this.setState({ questions: [...questions, this.state.input] })
  }

  render() {
    const allQuestions = this.state.questions.map((el, i) => {
      return <h1>{el}</h1>
    })
    return (
      <div>
        <h1>Wayne Foster</h1>
        {this.state.questionsAsked + " "} questions asked today.
        <button onClick={this.askQuestion}>Ask Question</button>
        <br/>
        <input value={this.state.input} placeholder="Enter a question." onChange={(e) => this.handleInput(e.target.value)}>
        <button onClick={this.addQuestion}>Add Question</button>
        <br/>
        {allQuestions}
      </div>
    );
  }
}
```

### Analyze, Evaluate, Create

Discuss these questions as a group

7.  Could your `Student` component be refactored into a functional component? Why or why not?

8.  What are the pros and cons of using a class method for an event handler vs. using an arrow function inline?

9.  The render() method is called every time a component's state is updated. For a text input, that means the render method is called for every keypress. Why isn't this bad for performance?
