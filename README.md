# Todo List App in Flask

A simple yet elegant web-based todo list application built with Flask and SQLAlchemy. This application allows users to create, update, toggle completion status, and delete tasks with a clean and intuitive user interface.

## ✨ Features

- **Create Tasks**: Add new tasks with a simple form
- **Edit Tasks**: Modify task titles after creation
- **Mark as Complete**: Toggle task completion status with a single click
- **Delete Tasks**: Remove tasks with confirmation
- **Persistent Storage**: All tasks are saved to a SQLite database
- **User Feedback**: Flash messages provide real-time feedback for actions
- **Responsive Design**: Clean, centered UI that works on different screen sizes
- **Task Organization**: Tasks are displayed with the newest first

## 📁 Project Structure

```
todo/
├── app.py                 # Main Flask application
├── instance/              # Instance folder (contains SQLite database)
│   └── todo.db           # SQLite database file
├── templates/            # HTML templates
│   ├── base.html         # Base template with styling
│   ├── index.html        # Main task list page
│   └── edit.html         # Task editing page
└── README.md             # This file
```

## 🛠️ Technologies Used

- **Backend**: Python 3, Flask
- **Database**: SQLite with SQLAlchemy ORM
- **Frontend**: HTML5, CSS3 (internal styling)
- **Templating**: Jinja2

## 📋 Requirements

- Python 3.7 or higher
- Flask
- Flask-SQLAlchemy

## 🚀 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/GmKandhro/Todo-List-app-in-Flask.git
cd todo
```

### Step 2: Create a Virtual Environment (Optional but Recommended)

```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install flask flask-sqlalchemy
```

### Step 4: Run the Application

```bash
python app.py
```

The application will be available at `http://localhost:5000` in your web browser.

## 📖 Usage Guide

### Adding a Task
1. Enter your task description in the text field at the top
2. Click the **Add Task** button
3. The task will appear at the top of the task list

### Viewing Tasks
- All tasks are displayed in a list format
- Completed tasks are visually distinguished with strikethrough styling
- Tasks are shown newest first

### Editing a Task
1. Click the **Edit** button next to any task
2. Modify the task title in the edit page
3. Click **Update** to save changes
4. You'll be redirected to the main page

### Marking Tasks as Complete
1. Click the **Complete** button next to any task
2. The task will be marked with strikethrough styling
3. Click **Undo** to mark the task as incomplete again

### Deleting a Task
1. Click the **Delete** button next to any task
2. Confirm the deletion when prompted
3. The task will be permanently removed from your list

## 🗄️ Database

The application uses SQLite to store tasks. The database file (`todo.db`) is automatically created in the `instance/` folder when you first run the application.

### Task Model
```python
- id: Unique identifier (Integer, Primary Key)
- title: Task description (String, Required)
- completed: Task completion status (Boolean, Default: False)
```

## 🔧 API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET | Display all tasks |
| `/add` | POST | Add a new task |
| `/edit/<id>` | GET, POST | Edit a task |
| `/toggle/<id>` | POST | Toggle task completion status |
| `/delete/<id>` | POST | Delete a task |

## 🎨 Features in Detail

### Flash Messages
The application provides user feedback through flash messages:
- **Success** (Green): Task added, updated successfully
- **Error** (Red): Validation errors (e.g., empty title)
- **Info** (Blue): Other updates (task toggled, deleted)

### Validation
- Task titles cannot be empty when adding or editing
- Tasks are validated before database operations
- 404 errors for non-existent task IDs

## 🐛 Troubleshooting

### Port 5000 Already in Use
If port 5000 is already in use, modify the last line in `app.py`:
```python
app.run(debug=True, port=5001)
```

### Database Issues
To reset the database and start fresh:
1. Delete the `instance/todo.db` file
2. Run the application again - a new database will be created

### Import Errors
Ensure all dependencies are installed:
```bash
pip install -r requirements.txt
# Or manually install:
pip install flask flask-sqlalchemy
```

## 🚀 Future Enhancements

Potential features for future versions:
- User authentication and multi-user support
- Task categories or tags
- Due dates and reminders
- Priority levels
- Search functionality
- Task filtering (show completed/incomplete only)
- Dark mode toggle
- Export tasks to CSV/PDF
- Drag-and-drop task reordering

## 📝 Notes

- The application runs in debug mode by default for development
- For production, change `debug=True` to `debug=False` in `app.py`
- The `SECRET_KEY` should be changed to a secure random string in production

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

**Gm Kandhro**

---

Happy task managing! 🎉
