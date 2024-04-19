document.addEventListener("DOMContentLoaded", function() {
    fetch("get_users.php")
        .then(response => response.json())
        .then(data => {
            const userList = document.getElementById("user-list");
            data.forEach(user => {
                const listItem = document.createElement("li");
                listItem.textContent = `${user.name} - ${user.email}`;
                userList.appendChild(listItem);
            });
        })
        .catch(error => console.error("Error fetching users:", error));
});
