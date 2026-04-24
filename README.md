<!DOCTYPE html>
<html>
<head>
    <title>Fitness Tracker</title>
    <style>
        body {
            font-family: Arial;
            text-align: center;
            margin-top: 50px;
        }
        input {
            padding: 10px;
            margin: 5px;
        }
        button {
            padding: 10px;
        }
        li {
            list-style: none;
            margin: 10px;
        }
    </style>
</head>
<body>

<h2>Fitness Tracker</h2>

<input type="text" id="activity" placeholder="Workout (e.g. Running)">
<input type="number" id="calories" placeholder="Calories">
<button onclick="addData()">Add</button>

<ul id="list"></ul>

<script>
function addData() {
    let act = document.getElementById("activity").value;
    let cal = document.getElementById("calories").value;

    if(act === "" || cal === "") {
        alert("Enter all fields");
        return;
    }

    let li = document.createElement("li");
    li.innerHTML = act + " - " + cal + " calories " +
    "<button onclick='this.parentElement.remove()'>Delete</button>";

    document.getElementById("list").appendChild(li);

    document.getElementById("activity").value = "";
    document.getElementById("calories").value = "";
}
</script>

</body>
</html>
