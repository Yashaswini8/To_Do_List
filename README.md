# Ex03 To-Do List using JavaScript
## Date:12-5-2026

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
## JAVASCRIPT:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To Do List</title>

    <link rel="stylesheet" href="style.css">

    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>

<body>

    <!-- FIRST PAGE -->

    <section class="landing-page">

        <div class="paper">

            <div class="stars">
                ✦ ✦ ✦
            </div>

            <h1>TO DO LIST</h1>

            <div class="dummy-list">

                <div class="line">
                    <div class="box"></div>
                    <hr>
                </div>

                <div class="line">
                    <div class="box"></div>
                    <hr>
                </div>

                <div class="line">
                    <div class="box"></div>
                    <hr>
                </div>

                <div class="line">
                    <div class="box"></div>
                    <hr>
                </div>

                <div class="line">
                    <div class="box"></div>
                    <hr>
                </div>

                <div class="line">
                    <div class="box"></div>
                    <hr>
                </div>

            </div>

            <button class="start-btn" onclick="scrollToApp()">
                Start Planning
            </button>

        </div>

    </section>


    <!-- SECOND PAGE -->

    <section class="app-section" id="app">

        <div class="todo-app">

            <h2>MY TASKS</h2>

            <div class="task-input-section">

                <input type="text" id="input-box" placeholder="Add a new task...">

                <button id="add-btn">Add</button>

            </div>

            <div class="filters">

                <button class="filter-btn active" onclick="filterTasks('all', this)">
                    All
                </button>

                <button class="filter-btn" onclick="filterTasks('completed', this)">
                    Completed
                </button>

                <button class="filter-btn" onclick="filterTasks('pending', this)">
                    Pending
                </button>

            </div>

            <ul id="list-container"></ul>

            <div class="bottom-section">

                <p id="task-count">0 Tasks Remaining</p>

                <button class="clear-btn" onclick="clearCompleted()">
                    Clear Completed
                </button>

            </div>

        </div>

    </section>

<script src="script.js"></script>

</body>
</html>
```
## CSS:
```
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins', sans-serif;
}

body{
    overflow-x:hidden;
    background:#f4f1ec;
}


/* FRONT PAGE */

.landing-page{
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:30px;
}

.image-container{
    position:relative;
    animation:float 4s ease-in-out infinite;
}

.image-container img{
    width:100%;
    max-width:500px;
    border-radius:20px;
    box-shadow:0 10px 30px rgba(0,0,0,0.2);
}

.start-btn{
    position:absolute;
    bottom:60px;
    left:50%;
    transform:translateX(-50%);
    padding:16px 40px;
    border:none;
    background:#4d6b34;
    color:white;
    border-radius:40px;
    font-size:18px;
    cursor:pointer;
    transition:0.3s;
    box-shadow:0 6px 15px rgba(0,0,0,0.2);
}

.start-btn:hover{
    transform:translateX(-50%) scale(1.05);
}


/* FLOAT ANIMATION */

@keyframes float{

    0%{
        transform:translateY(0px);
    }

    50%{
        transform:translateY(-10px);
    }

    100%{
        transform:translateY(0px);
    }
}



/* TODO APP */

.app-section{
    min-height:100vh;
    background:linear-gradient(135deg,#141e30,#243b55);
    display:flex;
    justify-content:center;
    align-items:center;
    padding:30px;
}

.todo-app{
    width:100%;
    max-width:650px;
    background:rgba(255,255,255,0.1);
    backdrop-filter:blur(15px);
    padding:40px;
    border-radius:25px;
    box-shadow:0 10px 40px rgba(0,0,0,0.4);
}

.todo-app h1{
    text-align:center;
    color:white;
    margin-bottom:30px;
    font-size:40px;
}


/* INPUT SECTION */

.task-input-section{
    display:flex;
    gap:15px;
    margin-bottom:25px;
}

.task-input-section input{
    flex:1;
    padding:16px;
    border:none;
    border-radius:12px;
    outline:none;
    font-size:16px;
}

.task-input-section button{
    padding:16px 25px;
    border:none;
    background:#00c6ff;
    color:white;
    border-radius:12px;
    cursor:pointer;
    font-size:16px;
}


/* FILTERS */

.filters{
    display:flex;
    justify-content:center;
    gap:10px;
    margin-bottom:20px;
}

.filter-btn{
    border:none;
    padding:10px 18px;
    border-radius:10px;
    cursor:pointer;
}

.filter-btn.active{
    background:#00c6ff;
    color:white;
}


/* TASK LIST */

#list-container li{
    list-style:none;
    background:rgba(255,255,255,0.15);
    color:white;
    margin-bottom:15px;
    padding:15px;
    border-radius:12px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    animation:slide 0.3s ease;
}

@keyframes slide{

    from{
        opacity:0;
        transform:translateX(-20px);
    }

    to{
        opacity:1;
        transform:translateX(0);
    }
}

.task-content{
    display:flex;
    gap:15px;
    align-items:center;
}

.completed{
    text-decoration:line-through;
    opacity:0.6;
}


/* BUTTONS */

.task-buttons{
    display:flex;
    gap:10px;
}

.edit-btn,
.delete-btn{
    border:none;
    padding:8px 12px;
    border-radius:8px;
    color:white;
    cursor:pointer;
}

.edit-btn{
    background:#28a745;
}

.delete-btn{
    background:#ff4d4d;
}


/* BOTTOM */

.bottom-section{
    margin-top:20px;
    display:flex;
    justify-content:space-between;
    color:white;
}

.clear-btn{
    border:none;
    padding:10px 16px;
    background:#ff4d4d;
    color:white;
    border-radius:10px;
    cursor:pointer;
}
```
## JAVASCRIPT:
```
const inputBox = document.getElementById("input-box");

const addBtn = document.getElementById("add-btn");

const listContainer = document.getElementById("list-container");

const taskCount = document.getElementById("task-count");

let currentFilter = "all";


// ADD BUTTON
addBtn.addEventListener("click", addTask);


// ENTER KEY
inputBox.addEventListener("keyup", function(event){

    if(event.key === "Enter"){

        addTask();
    }
});


// ADD TASK
function addTask(){

    const task = inputBox.value.trim();

    if(task === ""){

        alert("Please enter a task");

        return;
    }

    // CREATE TASK ITEM
    const li = document.createElement("li");

    li.innerHTML = `

        <div class="task-content">

            <input type="checkbox" class="check-task">

            <span>${task}</span>

        </div>

        <div class="task-buttons">

            <button class="edit-btn">Edit</button>

            <button class="delete-btn">Delete</button>

        </div>
    `;

    // ADD TO LIST
    listContainer.appendChild(li);

    // CLEAR INPUT
    inputBox.value = "";

    // ELEMENTS
    const checkbox = li.querySelector(".check-task");

    const text = li.querySelector("span");

    const deleteBtn = li.querySelector(".delete-btn");

    const editBtn = li.querySelector(".edit-btn");


    // COMPLETE TASK
    checkbox.addEventListener("change", function(){

        if(checkbox.checked){

            text.classList.add("completed");
        }
        else{

            text.classList.remove("completed");
        }

        updateTaskCount();

        applyFilter();
    });


    // DELETE TASK
    deleteBtn.addEventListener("click", function(){

        li.remove();

        updateTaskCount();
    });


    // EDIT TASK
    editBtn.addEventListener("click", function(){

        let updatedTask = prompt("Edit Task", text.innerText);

        if(updatedTask !== null && updatedTask.trim() !== ""){

            text.innerText = updatedTask;
        }
    });

    updateTaskCount();
}


// TASK COUNT
function updateTaskCount(){

    const totalTasks =
    listContainer.querySelectorAll("li").length;

    const completedTasks =
    listContainer.querySelectorAll(".check-task:checked").length;

    taskCount.innerText =
    `${totalTasks - completedTasks} Tasks Remaining`;
}


// FILTER TASKS
function filterTasks(filter, button){

    currentFilter = filter;

    // ACTIVE BUTTON
    document.querySelectorAll(".filter-btn").forEach(btn => {

        btn.classList.remove("active");
    });

    button.classList.add("active");

    applyFilter();
}


// APPLY FILTER
function applyFilter(){

    const tasks = listContainer.querySelectorAll("li");

    tasks.forEach(task => {

        const checkbox =
        task.querySelector(".check-task");

        if(currentFilter === "completed"){

            task.style.display =
            checkbox.checked ? "flex" : "none";
        }

        else if(currentFilter === "pending"){

            task.style.display =
            !checkbox.checked ? "flex" : "none";
        }

        else{

            task.style.display = "flex";
        }
    });
}


// CLEAR COMPLETED
function clearCompleted(){

    const completedTasks =
    document.querySelectorAll(".check-task:checked");

    completedTasks.forEach(task => {

        task.closest("li").remove();
    });

    updateTaskCount();
}
```

## OUTPUT
<img width="1915" height="1147" alt="image" src="https://github.com/user-attachments/assets/25ba5cf7-55c6-45bd-b1de-cca5f060d948" />
<img width="1910" height="1138" alt="image" src="https://github.com/user-attachments/assets/af002516-900e-4763-9e85-dbcc6d474da3" />
<img width="1908" height="1145" alt="image" src="https://github.com/user-attachments/assets/5582e58c-c5d0-4fd6-af07-5a709d7523a1" />

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
