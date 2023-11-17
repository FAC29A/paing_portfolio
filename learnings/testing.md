# Weeks 7-9: Learn how to make sure your code works correctly by creating automated tests.
Examples are based on these projects; [**To-Do List**](https://github.com/FAC29A/Lucy-Paing) and (for CSS Grid), FAC application portfolio, [**myWebsite**](https://github.com/Paing-Ko/myWebsite).

## TESTING



- [x] Check that passing a given input into our tests returns the expected output

```javaScript
//Test for checking off complete task

  test("Checking an entry marks it as complete", () => {
    // Arrange: Add a task
    addTask({ text: "Complete Me", completed: false });
    const taskIndex = toDoList.length - 1;

    // Act: Complete the task
    completeTask(taskIndex);

    // Assert: Check if the task is marked as completed
    equal(
      toDoList[taskIndex].completed,
      true,
      "Task should be marked as completed"
    );
  });
```

##### This test validates that a specific input, when processed by our application, produces the expected output, ensuring the reliability of our to-do list functionality.

- [x] Write tests to mimic the behaviour of a user performing different actions

```javaScript
// Test for filtering tasks
 test("Display tasks based on priority filter", () => {
    // Arrange
    toDoList.length = 0; // Reset the toDoList to ensure test isolation
    addTask({ text: "Low Priority", priority: "Low", completed: false });
    addTask({ text: "High Priority", priority: "High", completed: false });
    document.getElementById("priorityFilter").value = "all";

    // Act
    displayTasks();

    // Assert
    const taskList = document.getElementById("taskList");
    const displayedTasks = taskList.querySelectorAll("li");

    // The expected count should be the total number of tasks, since the filter is set to 'all'
    const expectedCount = toDoList.length;

    equal(
      displayedTasks.length,
      expectedCount,
      "All tasks should be displayed when filter is set to 'all'"
    );
    // Cleanup
    toDoList.length = 0; // Clear the toDoList
  });
```

##### This JavaScript test emulates user interactions, such as setting filters, to ensure the application accurately displays tasks based on user-selected priorities.

## JS
- [x] Write testable, modular functions

```javaScript
export function clearCompletedTasks() {
  for (let i = toDoList.length - 1; i >= 0; i--) {
    if (toDoList[i].completed) {
      toDoList.splice(i, 1);
    }
  }
  saveTasks();
}
```
##### The `clearCompletedTasks` function demonstrates an approach to writing clean, testable code by focusing on a single, clear purpose, which is essential for maintaining large codebases.

- [x] Write functions that add, remove or modify DOM nodes

```javaScript
//function to add Task
export function addTask(task) {
  console.log("Adding task:", task); // Debugging statement
  if (task.text.trim() !== "") {
    toDoList.push(task);
    saveTasks();
  }
}

// function to delete Task
export function deleteTask(index) {
  if (index >= 0 && index < toDoList.length) {
    toDoList.splice(index, 1);
    saveTasks();
  }
}

// DOM manipulation
function createDeleteButton(index) {
  const deleteButton = document.createElement("button");
  deleteButton.textContent = "Delete";
  deleteButton.classList.add("delete-btn");
  deleteButton.addEventListener("click", function () {
    deleteTask(index);
    displayTasks();
  });
  return deleteButton;
}

```
##### Functions like `addTask` and `deleteTask` showcase how to effectively interact with the Document Object Model (DOM) to dynamically update the user interface based on user actions.

- [x] Apply event listeners to HTML form elements

```javaScript
searchInput.addEventListener("input", function () {
  if (toDoList.length === 0 && searchInput.value.trim() !== "") {
    alert("Please add a task before searching.");
    searchInput.value = ""; // Clear the search input
  } else {
    displayTasks(); // Perform the search if tasks are present
  }
});
```
##### This example illustrates the application of event listeners to HTML elements, enhancing user interaction by responding to user input in real-time.

- [x] Use scope to control what variables are accessible inside functions and blocks

```javaScript
// Hide or show the task list wrapper based on the number of tasks
function toggleTaskListVisibility() {
  const taskListWrapper = document.getElementById("taskListWrapper");
  if (toDoList.length > 0) {
    taskListWrapper.style.display = "block";
  } else {
    taskListWrapper.style.display = "none";
  }
}

```
##### The `toggleTaskListVisibility` function demonstrates the effective use of scope to manage variable accessibility, ensuring that UI elements reflect the current state of the task list.

## DESIGN
- [x] Use CSS grid to create complex layouts

```javaScript
.project-grid {
    display: grid;
    gap: 50px;
}

.project-grid-3 {
    grid-template-columns: 1fr 1fr 1fr;
    /* 3 columns */
}

.project-grid-4 {
    grid-template-columns: 1fr 1fr 1fr 1fr;
    /* 4 columns */
}

.project {
    border: 1px solid #ccc;
    padding: 20px;
    border-radius: 4px;
}

```

#####  Utilizing CSS grid to create a multi-column layout demonstrates how to build visually appealing and complex web page structures in a straightforward manner.

- [x] Use CSS grid to make layouts that adapt to the viewport size

```javaScript
/* Adjust the grid when the viewport is 800px or less */
@media screen and (max-width: 800px) {

    .project-grid {
        grid-template-columns: 1fr;
        /* this creates two columns */
    }

    #second-row {
        display: none;
    }
}
```
##### This CSS snippet shows how to adapt grid layouts to different viewport sizes using media queries, ensuring a responsive and user-friendly interface across various devices.
