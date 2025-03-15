# DTI-project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Campus Swap</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f7f7f7;
            color: #333;
        }
        .container {
            width: 80%;
            margin: auto;
        }
        .header {
            background: #6a0572;
            color: white;
            text-align: center;
            padding: 1.5em 0;
            font-size: 24px;
            font-weight: bold;
        }
        .nav {
            display: flex;
            justify-content: space-evenly;
            color :white;
            background: #9b72aa;
            padding: 1em;
            border-radius: 0 0 10px 10px;
        }
        .nav a {
            color: white;
            font-size: large;
            text-decoration: none;
            font-weight: bold;
            padding: 0.5em 1.5em;
            transition: 0.3s ease;
        }
        .nav a:hover {
            background: white;
            color: #6a0572;
            border-radius: 5px;
        }
        .section {
            background: white;
            padding: 2em;
            margin: 1em 0;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
        .search-bar {
            text-align: center;
            margin: 1em 0;
        }
        .search-bar input {
            width: 80%;
            padding: 12px;
            font-size: 16px;
            border-radius: 8px;
            border: 1px solid #ddd;
            outline: none;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1em;
        }
        .item-card {
            background: #ffe4e1;
            padding: 1.5em;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: 0.3s;
            font-weight: bold;
            color: #6a0572;
        }
        .item-card img {
            width: 95%;
            height: 400px;
            object-fit: cover;
            border-radius: 10px;
        }
        .item-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }
        .form-group {
            margin: 1em 0;
        }
        .form-group input, .form-group textarea {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            border-radius: 5px;
            border: 1px solid #ccc;
            outline: none;
        }
        .btn {
            background: #6a0572;
            color: white;
            padding: 12px 24px;
            border: none;
            cursor: pointer;
            border-radius: 8px;
            font-size: 16px;
            transition: 0.3s ease;
        }
        .btn:hover {
            background: #9b72aa;
        }
        .footer {
            background: #6a0572;
            color: white;
            text-align: center;
            padding: 1em 0;
            margin-top: 2em;
            border-radius: 10px 10px 0 0;
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Campus Swap</h1>
    </header>
    <nav class="nav">
        <a href="index.html">Home</a>
        <a href="buy.html">Buy</a>
        <a href="sell.html">Sell</a>
        <a href="exchange.html">Exchange</a>
        <a href="rent.html">Rent</a>
        <a href="messages.html">Messages</a>
        <a href="profile.html">Profile</a>
    </nav>
    <div class="container">
        <div class="search-bar">
            <input type="text" placeholder="Search for items...">
        </div>
        <section class="section">
            <h2>Featured Listings</h2>
            <div class="grid">
                <div class="item-card">
                    <img src="laptop.jpg" alt="Laptop">
                    <p>Laptop - Rs.25,000</p>
                </div>
                <div class="item-card">
                    <img src="textbook.jpg" alt="Textbooks">
                    <p>Textbooks - Rs.300</p>
                </div>
                <div class="item-card">
                    <img src="bike.jpg" alt="Bike">
                    <p>Bike - Rs.10,000</p>
                </div>
            </div>
        </section>
        <section class="section">
            <h2>Post a New Listing</h2>
            <form>
                <div class="form-group">
                    <input type="text" placeholder="Title" required>
                </div>
                <div class="form-group">
                    <input type="text" placeholder="Category" required>
                </div>
                <div class="form-group">
                    <input type="number" placeholder="Price" required>
                </div>
                <div class="form-group">
                    <textarea placeholder="Description" required></textarea>
                </div>
                <button class="btn" type="submit">Post</button>
            </form>
        </section>
    </div>
    <footer class="footer">
        <p>© 2025 Uni Connect | All Rights Reserved</p>
    </footer>
</body>
</html>

# profile code
<section class="section">
    <h2>User Profile</h2>
    <div class="profile-container">
        <img id="profile-pic" src="default-avatar.png" alt="Profile Picture">
        <input type="file" id="upload-pic" accept="image/*">
        <h3 id="user-name">Vanshika Dhull</h3>
        <p id="user-email">vanshikadhull28112005@gmail.com</p>
        <p id="user-bio">Student at Bennett University. Interested in Web Development.</p>
        <button class="btn" onclick="editProfile()">Edit Profile</button>
    </div>
</section>

<!-- Edit Profile Modal -->
<div id="edit-modal" class="modal">
    <div class="modal-content">
        <h2>Edit Profile</h2>
        <input type="text" id="edit-name" placeholder="Full Name">
        <input type="email" id="edit-email" placeholder="Email">
        <textarea id="edit-bio" placeholder="Bio"></textarea>
        <button class="btn" onclick="saveProfile()">Save</button>
    </div>
</div>

<script>
    function editProfile() {
        document.getElementById("edit-modal").style.display = "block";
        document.getElementById("edit-name").value = document.getElementById("user-name").textContent;
        document.getElementById("edit-email").value = document.getElementById("user-email").textContent;
        document.getElementById("edit-bio").value = document.getElementById("user-bio").textContent;
    }

    function saveProfile() {
        document.getElementById("user-name").textContent = document.getElementById("edit-name").value;
        document.getElementById("user-email").textContent = document.getElementById("edit-email").value;
        document.getElementById("user-bio").textContent = document.getElementById("edit-bio").value;
        document.getElementById("edit-modal").style.display = "none";
    }

    document.getElementById("upload-pic").addEventListener("change", function(event) {
        const file = event.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(e) {
                document.getElementById("profile-pic").src = e.target.result;
            };
            reader.readAsDataURL(file);
        }
    });
</script>
<style>
.profile-container {
    background: #f4f4f4;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    max-width: 400px;
    margin: 20px auto;
    height: 400px;
}

#profile-pic {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #805091;
}

#upload-pic {
    margin-top: 10px;
}

h3, p {
    margin: 10px 0;
    color: #333;
}

.btn {
    background: #805091;
    color: white;
    border: none;
    padding: 10px 15px;
    cursor: pointer;
    border-radius: 5px;
    transition: background 0.3s ease;
}

.btn:hover {
    background: #6a3b7d;
}

.modal {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 20px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);
    border-radius: 10px;
    text-align: center;
    width: 300px;
}

.modal input, .modal textarea {
    width: 100%;
    padding: 8px;
    margin: 8px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.modal textarea {
    resize: none;
    height: 80px;
}

.modal .btn {
    width: 100%;
}
</style>

# login code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - Campus Marketplace</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: white;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .login-container {
            background: #975fab;
            padding: 2em;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
            width: 500px;
            height: 500px;
            text-align: center;
        }
        .login-container h2 {
            margin-bottom: 1em;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: none;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 10px;
            background: #9b72aa;
            border: none;
            color: white;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #6a0572;
        }
        .register-link {
            margin-top: 10px;
            display: block;
            color: white;
            text-decoration: none;
        }
        .register-link:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h1>Login</h1>
        <form>
            <input type="text" placeholder="Username" required>
            <input type="password" placeholder="Password" required>
            <button type="submit">Login</button>
        </form>
        <a href="register.html" class="register-link">Don't have an account? Register</a>
    </div>
</body>
</html>
#register code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Register - Campus Marketplace</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #ececec;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background: white;
            padding: 2em;
            border-radius: 8px;
            box-shadow: 0 0 10px #9b72aa;
            width: 350px;
            text-align: center;
        }
        h2 {
            margin-bottom: 1em;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            background: #6a0572;
            color: white;
            border: none;
            padding: 10px;
            width: 100%;
            cursor: pointer;
            border-radius: 5px;
            font-size: 16px;
        }
        button:hover {
            background: #6a0572;
        }
        p {
            margin-top: 10px;
        }
        a {
            color: #6a0572;
            text-decoration: none;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Create an Account</h2>
        <form action="register_process.php" method="POST">
            <input type="text" name="fullname" placeholder="Full Name" required>
            <input type="email" name="email" placeholder="Email Address" required>
            <input type="password" name="password" placeholder="Password" required>
            <input type="password" name="confirm_password" placeholder="Confirm Password" required>
            <button type="submit">Register</button>
        </form>
        <p>Already have an account? <a href="login.html" >Login here</a></p>
    </div>
</body>
</html>
# messages code
<section class="section">
    <h1>Messages</h1>

    <!-- Message Display Box -->
    <div class="message-box" id="message-box"></div>

    <!-- Input Box -->
    <div class="message-input">
        <input type="text" id="message-input" placeholder ="Type a message..." onkeypress="handleEnter(event)">
        <button class="btn" onclick="sendMessage()">Send</button>
    </div>
</section>

<script>
    document.addEventListener("DOMContentLoaded", function () {
        const messages = [
            { sender: "User", text: "Hey, is the laptop still available?" },
            { sender: "Seller", text: "Yes! It's in great condition." },
            { sender: "User", text: "Awesome! Can we negotiate the price?" }
        ];

        function displayMessages() {
            const messageBox = document.getElementById("message-box");
            messageBox.innerHTML = "";
            messages.forEach(msg => {
                const div = document.createElement("div");
                div.classList.add("message", msg.sender === "User" ? "user-message" : "seller-message");
                div.innerText = msg.text;
                messageBox.appendChild(div);
            });
            messageBox.scrollTop = messageBox.scrollHeight;
        }

        window.sendMessage = function () {
            const input = document.getElementById("message-input");
            const messageText = input.value.trim();
            if (messageText) {
                messages.push({ sender: "User", text: messageText });
                displayMessages();
                input.value = "";
            }
        };

        window.handleEnter = function (event) {
            if (event.key === "Enter") {
                sendMessage();
            }
        };

        displayMessages();
    });
</script>

<style>
    
    .message-box {
        height: 86%;
        overflow-y: auto;
        border: 1px solid black;
        padding: 10px;
        border-radius: 10px;
        background: #9b72aa;
    }
    .message {
        padding: 10px;
        margin: 5px;
        border-radius: 8px;
        max-width: 70%;
        font-size: 30px;
    }
    .user-message {
        background: #805091;
        color: white;
        align-self: flex-end;
        text-align: right;
        margin-left: auto;
        height: 60px;
    }
    .seller-message {
        background: #e0e0e0;
        align-self: flex-start;
        height: 60px;
    }
    .message-input {
        display: flex;
        margin-top: 10px;
        height: 60px;
        color: white;
    }
    .message-input input {
        flex-grow: 1;
        padding: 10px;
        border-radius: 5px;
        border: 1px solid #ccc;
        font-size: 16px;
        background-color: #9b72aa;
    }
    .btn{
        width: 100px;
    }
    .message-input input::placeholder {
    color: white;
    opacity: 1; /* Ensure full opacity */
    }
</style>
#rent code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Campus Swap</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f8f9fa;
            font-size: 50px;
        }
        .section {
            background: white;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        h2 {
            text-align: center;
            color: #333;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            padding: 10px;
        }
        .item-card {
            background: white;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            font-weight: bold;
            color: #555;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            transition: 0.3s ease;
            height: 60px;
        }
        .item-card:hover {
            transform: scale(1.05);
            background: #f0f0f0;
        }
        .form-group {
            margin-bottom: 15px;
        }
        input, textarea, button {
            width: 100%;
            height: 100px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 24px;
        }
        textarea {
            resize: none;
            height: 120px;
        }
        .btn {
            background: #6a0572;
            color: white;
            font-weight: bold;
            border: none;
            cursor: pointer;
            transition: 0.3s ease;
        }
        .btn:hover {
            background: #6a0572;
        }
    </style>
</head>
<body>
    <section class="section">
        <h2>Sell an Item</h2>
        <form id="sell-form">
            <div class="form-group">
                <input type="text" id="sell-title" placeholder="Item Name" required>
            </div>
            <div class="form-group">
                <input type="text" id="sell-category" placeholder="Category" required>
            </div>
            <div class="form-group">
                <input type="number" id="sell-price" placeholder="Price ($)" required>
            </div>
            <div class="form-group">
                <textarea id="sell-description" placeholder="Description" required></textarea>
            </div>
            <button class="btn" type="submit">Post for Sale</button>
        </form>
    </section>

  <section class="section">
        <h2>Available Rentals</h2>
        <div class="grid" id="rental-list">
            <div class="item-card">Projector - $10/day</div>
            <div class="item-card">Camera - $15/day</div>
            <div class="item-card">Study Room - $5/hour</div>
        </div>
    </section>

  <section class="section">
        <h2>Request a Rental</h2>
        <form id="rent-form">
            <div class="form-group">
                <input type="text" id="item-name" placeholder="Item Name" required>
            </div>
            <div class="form-group">
                <input type="number" id="rental-price" placeholder="Price per day ($)" required>
            </div>
            <div class="form-group">
                <textarea id="rental-description" placeholder="Description" required></textarea>
            </div>
            <button class="btn" type="submit">Post Rental</button>
        </form>
    </section>

  <script>
        document.getElementById("sell-form").addEventListener("submit", function(event) {
            event.preventDefault();
            const title = document.getElementById("sell-title").value;
            const price = document.getElementById("sell-price").value;
            const category = document.getElementById("sell-category").value;
            const description = document.getElementById("sell-description").value;

            if (title && price && category && description) {
                const itemList = document.getElementById("item-list");
                const newItem = document.createElement("div");
                newItem.classList.add("item-card");
                newItem.textContent = `${title} - $${price}`;
                itemList.appendChild(newItem);

                document.getElementById("sell-form").reset();
            }
        });

        document.getElementById("rent-form").addEventListener("submit", function(event) {
            event.preventDefault();
            const itemName = document.getElementById("item-name").value;
            const rentalPrice = document.getElementById("rental-price").value;
            const description = document.getElementById("rental-description").value;

            if (itemName && rentalPrice && description) {
                const rentalList = document.getElementById("rental-list");
                const newItem = document.createElement("div");
                newItem.classList.add("item-card");
                newItem.textContent = `${itemName} - $${rentalPrice}/day`;
                rentalList.appendChild(newItem);

                document.getElementById("rent-form").reset();
            }
        });
    </script>
</body>
</html>
# Exchange code
<section class="section">
    <h1>Available Items for Exchange</h1>

    <!-- Search and Filter -->
    <div class="search-bar">
        <input type="text" id="search-input" placeholder="Search for items..." onkeyup="filterItems()">
        <select id="category-filter" onchange="filterItems()">
            <option value="">All Categories</option>
            <option value="Electronics">Electronics</option>
            <option value="Books">Books</option>
            <option value="Furniture">Furniture</option>
        </select>
    </div>

    <!-- Items Grid -->
    <div class="grid" id="items-list"></div>
</section>

<!-- Exchange Request Modal -->
<div id="exchangeModal" class="modal">
    <div class="modal-content">
        <span class="close" onclick="closeModal()">&times;</span>
        <h2>Propose an Exchange</h2>
        <p id="selectedItem"></p>
        <input type="text" id="offerItem" placeholder="Enter the item you want to offer" required>
        <button class="btn" onclick="submitExchange()">Submit Request</button>
    </div>
</div>

<script>
    document.addEventListener("DOMContentLoaded", function () {
        const items = [
            { name: "Tablet", category: "Electronics" },
            { name: "Programming Book", category: "Books" },
            { name: "Office Chair", category: "Furniture" },
            { name: "Smartwatch", category: "Electronics" },
            { name: "Wooden Desk", category: "Furniture" }
        ];

        const itemsList = document.getElementById("items-list");

        function displayItems(filteredItems) {
            itemsList.innerHTML = "";
            filteredItems.forEach(item => {
                const div = document.createElement("div");
                div.classList.add("item-card");
                div.innerHTML = `
                    <strong>${item.name}</strong> <br>
                    <small>Category: ${item.category}</small> <br>
                    <button class="btn" onclick="openExchangeModal('${item.name}')">Request Exchange</button>
                `;
                itemsList.appendChild(div);
            });
        }

        function filterItems() {
            const searchQuery = document.getElementById("search-input").value.toLowerCase();
            const selectedCategory = document.getElementById("category-filter").value;

            const filteredItems = items.filter(item => 
                item.name.toLowerCase().includes(searchQuery) &&
                (selectedCategory === "" || item.category === selectedCategory)
            );

            displayItems(filteredItems);
        }

        window.openExchangeModal = function(itemName) {
            document.getElementById("exchangeModal").style.display = "block";
            document.getElementById("selectedItem").innerText = `Propose an exchange for: ${itemName}`;
        };

        window.closeModal = function() {
            document.getElementById("exchangeModal").style.display = "none";
        };

        window.submitExchange = function() {
            const offerItem = document.getElementById("offerItem").value;
            if (offerItem) {
                alert(`Exchange request sent: You offered "${offerItem}"`);
                closeModal();
            } else {
                alert("Please enter an item to offer.");
            }
        };

        displayItems(items);
    });
</script>

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f8f9fa;
        margin: 0;
        padding: 20px;
        text-align: center;
    }

    .section {
        max-width: 100%;
        height: 100%;
        margin: auto;
        background: white;
        background-color: #9b72aa;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    .search-bar {
        text-align: center;
        margin-bottom: 20px;
    }

    .search-bar input, .search-bar select {
        padding: 12px;
        font-size: 18px;
        border-radius: 8px;
        border: none;
        margin-right: 10px;
        width: 50%;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 33px;
        padding: 30px;
        justify-content: center;
        width: 90%;
    }

    .item-card {
        background: #fff;
        padding: 30px;
        border-radius: 15px;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        text-align: center;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        color: black;
        width: 420px;
        height: 300px;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .btn {
        background: #6a0572;
        color: white;
        padding: 12px 20px;
        border: none;
        cursor: pointer;
        border-radius: 8px;
        font-size: 16px;
        margin-top: 10px;
    }

    .btn:hover {
        background: #9b72aa;
    }

    .modal {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.5);
        justify-content: center;
        align-items: center;
    }

    .modal-content {
        background: white;
        padding: 20px;
        width: 300px;
        border-radius: 10px;
        text-align: center;
        position: relative;
    }

    .close {
        position: absolute;
        right: 10px;
        top: 10px;
        font-size: 24px;
        cursor: pointer;
    }
</style>


