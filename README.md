# List-App-pro2
This is a List App 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>List App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        #list-container {
            max-width: 400px;
            margin: auto;
        }

        #item-input {
            width: 70%;
            padding: 8px;
        }

        #add-btn {
            width: 28%;
            padding: 8px;
            margin-left: 2%;
        }

        #item-list {
            list-style-type: none;
            padding: 0;
        }

        .list-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #ccc;
            padding: 8px 0;
        }

        .list-item button {
            background-color: #f44336;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div id="list-container">
    <h2>List App</h2>
    <div>
        <input type="text" id="item-input" placeholder="Enter item">
        <button onclick="addItem()" id="add-btn">Add</button>
    </div>
    <ul id="item-list"></ul>
</div>

<script>
    function addItem() {
        var inputElement = document.getElementById('item-input');
        var inputValue = inputElement.value;

        if (inputValue.trim() !== '') {
            var itemList = document.getElementById('item-list');

            var listItem = document.createElement('li');
            listItem.className = 'list-item';

            var itemText = document.createElement('span');
            itemText.textContent = inputValue;

            var deleteButton = document.createElement('button');
            deleteButton.textContent = 'Delete';
            deleteButton.onclick = function () {
                itemList.removeChild(listItem);
            };

            listItem.appendChild(itemText);
            listItem.appendChild(deleteButton);
            itemList.appendChild(listItem);

            inputElement.value = ''; // Clear input field
        }
    }
</script>

</body>
</html>
