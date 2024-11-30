# Sticky-Notes
#Final.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sticky Notes</title>
    <link rel="stylesheet" href="Final.css">
    <script>
        function createNote() {
  const stickyNotes = document.querySelector('.sticky-notes');
  const noteContainer = document.createElement('div');
  noteContainer.classList.add('note-container');

  const noteContent = document.createElement('div');
  noteContent.classList.add('note-content');
  noteContent.contentEditable = true;
  noteContent.textContent = 'New note';

  const noteActions = document.createElement('div');
  noteActions.classList.add('note-actions');
  const deleteButton = document.createElement('button');
  deleteButton.classList.add('delete-note');
  deleteButton.textContent = 'Delete';
  deleteButton.onclick = function () {
    noteContainer.remove();
  };

  noteActions.appendChild(deleteButton);
  noteContainer.appendChild(noteContent);
  noteContainer.appendChild(noteActions);
  stickyNotes.appendChild(noteContainer);
}

function deleteNote(button) {
  const noteContainer = button.closest('.note-container');
  noteContainer.remove();
}
    </script>
</head>
<body>
    <div class="sticky-notes">
        <div class="note-container">
          <div class="note-content" contenteditable>
            Write Your Note
          </div>
          <div class="note-actions">
            <button class="delete-note" onclick="deleteNote(this)">Delete</button>
          </div>
        </div>
      </div>
      <div class="create-note" title="New Notes" onclick="createNote()">+</div>
</body>
</html>

#Final.css

*{
    margin: 0;
    padding: 0;
  }
  
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    background: #1f1d2b;
    font-family: 'Gloria Hallelujah', cursive;
    min-height: 100vh;
  }
  
  .sticky-notes {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    max-width: 800px;
  }
  
  .note-container {
    position: relative;
    width: 250px;
    height: 250px;
    background: linear-gradient(#f9efaf, #f7e98d);
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    overflow: hidden;
  }
  
  .note-container:hover {
    box-shadow: 0 5px 8px rgba(0, 0, 0, 0.15);
  }
  
  .note-content {
    padding: 15px;
    height: calc(100% - 40px);
    border: none;
    outline: none;
  }
  
  .note-actions {
    position: absolute;
    bottom: 10px;
    right: 10px;
  }
  
  .delete-note {
    background-color: #ff6347;
    color: #fff;
    border: none;
    padding: 8px 12px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 14px;
    transition: background-color 0.3s ease;
  }
  
  .delete-note:hover {
    background-color: #d9534f;
  }
  
  .create-note {
    display: flex;
    justify-content: center;
    align-items: center;
    font: 120px 'Helvetica', sans-serif;
    margin: 0 15px;
    width: 250px;
    height: 250px;
    background-color: #fff;
    color: #888;
    cursor: pointer;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease-in-out;
  }
  
  .create-note:hover {
    transform: scale(1.05);
    box-shadow: 0 6px 10px rgba(0, 0, 0, 0.2);
  }



