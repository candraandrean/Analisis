document.getElementById('add-task-btn').addEventListener('click', function() {
    const taskInput = document.getElementById('new-task');
    const taskText = taskInput.value.trim();
    
    if (taskText !== '') {
        const taskList = document.getElementById('task-list');
        const taskItem = document.createElement('li');
        taskItem.textContent = taskText;
        
        const removeBtn = document.createElement('button');
        removeBtn.textContent = 'Remove';
        removeBtn.classList.add('remove-btn');
        removeBtn.addEventListener('click', function() {
            taskList.removeChild(taskItem);
        });
        
        taskItem.appendChild(removeBtn);
        taskItem.addEventListener('click', function() {
            taskItem.classList.toggle('completed');
        });
        
        taskList.appendChild(taskItem);
        taskInput.value = '';
    }
});
