# Golang State Machine

## Overview

This project is designed to help you learn about state machines and their implementation in Go. It includes a basic implementation of a state machine that manages states and transitions based on events. 

The provided example models a ticket system with three states (`Open`, `InProgress`, and `Closed`) and corresponding events (`StartProgress`, `Close`, and `Reopen`). The state machine handles transitions between these states and executes actions associated with each transition.

## Components

### State Machine Definition

The state machine is defined using the following types and constants:

- **States**: `Open`, `InProgress`, and `Closed`
- **Events**: `StartProgress`, `Close`, and `Reopen`
- **Actions**: Functions associated with state transitions

### Code Explanation

1. **State and Event Types**:
   ```go
   type State int
   type Event int
   ```

   These types represent the different states and events in the state machine.

2. **StateMachine Structure**:
   ```go
   type StateMachine struct {
       currentState State
       transitions  map[State]map[Event]State
       actions      map[State]map[Event]Action
   }
   ```

   The `StateMachine` struct holds the current state, state transitions, and actions for each state-event combination.

3. **NewStateMachine Function**:
   ```go
   func NewStateMachine(initialState State) *StateMachine
   ```

   Initializes a new state machine with the given initial state, sets up transitions and actions.

4. **SendEvent Method**:
   ```go
   func (sm *StateMachine) SendEvent(event Event)
   ```

   Processes an event, performs state transitions, and executes associated actions.

5. **Main Function**:
   ```go
   func main() {
       sm := NewStateMachine(Open)
       sm.SendEvent(StartProgress)
       sm.SendEvent(Close)
       sm.SendEvent(Reopen)
   }
   ```

   Demonstrates the use of the state machine by creating an instance and sending events to it.

## How to Use

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/diegodazpeitia/golang-machine-state.git
   ```

2. **Navigate to the Project Directory**:
   ```bash
   cd golang-machine-state
   ```

3. **Run the Example**:
   ```bash
   go run main.go
   ```

   This will execute the example and show the output of state transitions and actions.

## Learning Objectives

- Understand the concept of a state machine and its components.
- Learn how to implement a state machine in Go.
- Explore state transitions and event handling.
- See how to define and execute actions based on state transitions.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to open issues or submit pull requests if you have suggestions or improvements.
