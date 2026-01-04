# Data Model: Phase I - In-Memory Python Console Todo App

## Task Entity

### Fields
- **id**: int (auto-generated, unique identifier)
- **description**: str (task description text)
- **completed**: bool (completion status, default: False)
- **created_at**: datetime (timestamp when task was created, auto-generated)

### Relationships
- None (standalone entity)

### Validation Rules
- description: Required, non-empty string
- id: Must be unique within the todo list
- completed: Must be boolean value (True/False)

### State Transitions
- New Task: created with completed=False
- Complete: transition from completed=False to completed=True
- Incomplete: transition from completed=True to completed=False (optional functionality)

## TodoList Collection

### Fields
- **tasks**: List[Task] (collection of Task entities)
- **next_id**: int (next available ID for new tasks, auto-incrementing)

### Operations
- Add Task: Add a new Task to the collection with auto-generated ID
- Get All Tasks: Return all tasks in the collection
- Get Task by ID: Return specific task by its ID
- Update Task: Modify an existing task's description
- Delete Task: Remove a task from the collection by ID
- Mark Complete: Update a task's completion status to True
- Mark Incomplete: Update a task's completion status to False (optional)