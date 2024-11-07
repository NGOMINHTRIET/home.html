<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>$#%^&*()*&^%&^%#$%@#^#&%*&*^(&)#$%$#^$&^%*&%@#$^^$%$&%$%#@%@%$#%^^&^%&%$#&^*&^**&*^&%*^$%&#^$%^#^#^</title>
    <style>
        body {
            flex-wrap: wrap;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #eaeaea;
            margin: 0;
            padding: 0;
        }

        /* Thanh điều hướng */
        nav {
            background-color: #4CAF50;
            color: white;
            padding: 15px;
            text-align: center;
        }

        nav h1 {
            margin: 0;
        }

        /* Layout quản trị */
        .container {
            display: flex;
            min-height: 100vh;
        }

        /* Sidebar */
        .sidebar {
            background-color: #34495e;
            width: 250px;
            padding: 20px;
            color: white;
            box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
        }

        .sidebar ul {
            list-style-type: none;
            padding: 0;
        }

        .sidebar ul li {
            margin: 15px 0;
        }

        .sidebar ul li a {
            color: white;
            text-decoration: none;
            display: block;
            padding: 10px;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        .sidebar ul li a:hover {
            background-color: #2c3e50;
        }

        /* Nội dung chính */
        .main-content {
            flex: 1;
            padding: 20px;
            background-color: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            margin: 20px;
        }

        .main-content h2 {
            margin-top: 0;
            color: #333;
        }

        /* Bảng hiển thị dữ liệu */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }

        table, th, td {
            border: 1px solid #ddd;
        }

        th, td {
            padding: 10px;
            text-align: left;
        }

        th {
            background-color: #f4f4f4;
            color: #333;
        }

        /* Form */
        .form-container {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            max-width: 500px;
            margin: 20px auto;
        }

        .form-container input, .form-container select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .form-container button {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .form-container button:hover {
            background-color: #388e3c;
        }

        /* Form đăng nhập */
        #login-form {
            display: flex;
            flex-direction: column;
            max-width: 400px;
            margin: 50px auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        #login-form input {
            margin-bottom: 15px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        #login-form button {
            margin-top: 10px;
            background-color: #4CAF50;
            border: none;
            color: white;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        #login-form button:hover {
            background-color: #388e3c;
        }

        #login-error-message {
            color: red;
            display: none;
            text-align: center;
        }
    </style>
</head>
<body>

    <!-- Thanh điều hướng -->
    <nav>
        <h1>HACK GAMES SCRIPT</h1>
    </nav>

    <!-- Form đăng nhập -->
    <div id="login-form">
        <h2>Đăng nhập</h2>
        <input type="text" id="admin-username" placeholder="Tên đăng nhập" required />
        <input type="password" id="admin-password" placeholder="Mật khẩu" required />
        <button onclick="login()">Đăng nhập</button>
        <p id="login-error-message">Sai tên đăng nhập hoặc mật khẩu</p>
    </div>

    <!-- Layout -->
    <div class="container" id="admin-panel" style="display: none;">

        <!-- Sidebar -->
        <div class="sidebar">
            <ul>
                <li><a href="#" onclick="showSection('dashboard')">Bảng điều khiển</a></li>
                <li><a href="#" onclick="showSection('manage-users')">Quản lý người dùng</a></li>
                <li><a href="#" onclick="showSection('manage-games')">Quản lý game</a></li>
                <li><a href="#" onclick="showSection('statistics')">Script</a></li>
                <li><a href="#" onclick="logout()">Đăng xuất</a></li>
            </ul>
        </div>

        <!-- Nội dung chính -->
        <div class="main-content">

            <!-- Bảng điều khiển -->
            <div id="dashboard">
                <h2>Bảng điều khiển</h2>
                <p>Chào mừng đến với trang quản trị! Tại đây bạn có thể quản lý người dùng, game và xem các thống kê.</p>
            </div>

            <!-- Quản lý người dùng -->
            <div id="manage-users" style="display: none;">
                <h2>Quản lý người dùng</h2>
                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Tên đăng nhập</th>
                            <th>Email</th>
                            <th>Hành động</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td>
                            <td>user1</td>
                            <td>user1@gmail.com</td>
                            <td><button onclick="deleteUser(1)">Xóa</button></td>
                        </tr>
                        <tr>
                            <td>2</td>
                            <td>user2</td>
                            <td>user2@gmail.com</td>
                            <td><button onclick="deleteUser(2)">Xóa</button></td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <!-- Quản lý game -->
            <div id="manage-games" style="display: none;">
                <h2>Quản lý game</h2>

                <div class="form-container">
                    <h3>Thêm game mới</h3>
                    <input type="text" id="game-name" placeholder="Tên game" required />
                    <input type="text" id="game-url" placeholder="URL tải về" required />
                    <button onclick="addGame()">Thêm game</button>
                </div>

                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Tên game</th>
                            <th>URL</th>
                            <th>Hành động</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td>
                            <td>Game 1</td>
                            <td><a href="#">Link tải về</a></td>
                            <td><button onclick="deleteGame(1)">Xóa</button></td>
                        </tr>
                        <tr>
                            <td>2</td>
                            <td>Game 2</td>
                            <td><a href="#">Link tải về</a></td>
                            <td><button onclick="deleteGame(2)">Xóa</button></td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <!-- Thống kê -->
            <div id="statistics" style="display: none;">
                <h2>Script</h2>
                <p></p>
                <img src="imp/solara.webp" alt="VSCodeUserSetup-x64-1">
                <u><li>solara là phân mềm hack kết nói vào file roblox và chỉnh sữa file games của trong chơi của nhà sáng tạo game</li></u>
                
            </div>

        </div>

    </div>

    <script>
        const adminUsername = "SCRIPT_NMT"; // Tên đăng nhập admin
        const adminPassword = "MVPROBLOX.COM"; // Mật khẩu admin

        function login() {
            const username = document.getElementById('admin-username').value;
            const password = document.getElementById('admin-password').value;
            const errorMessage = document.getElementById('login-error-message');

            if (username === adminUsername && password === adminPassword) {
                document.getElementById('login-form').style.display = 'none';
                document.getElementById('admin-panel').style.display = 'flex';
                showSection('dashboard'); // Mặc định hiển thị bảng điều khiển
            } else {
                errorMessage.style.display = 'block'; // Hiển thị thông báo lỗi
            }
        }

        function showSection(section) {
            // Ẩn tất cả các phần
            document.getElementById('dashboard').style.display = 'none';
            document.getElementById('manage-users').style.display = 'none';
            document.getElementById('manage-games').style.display = 'none';
            document.getElementById('statistics').style.display = 'none';

            // Hiển thị phần được chọn
            document.getElementById(section).style.display = 'block';
        }

        function deleteUser(userId) {
            alert(`Xóa người dùng ID: ${userId}`);
        }

        function deleteGame(gameId) {
            alert(`Xóa game ID: ${gameId}`);
        }

        function addGame() {
            let gameName = document.getElementById('game-name').value;
            let gameUrl = document.getElementById('game-url').value;

            if (gameName && gameUrl) {
                alert(`Thêm game: ${gameName}, URL: ${gameUrl}`);
                // Thực tế, ở đây bạn sẽ thêm game vào cơ sở dữ liệu
            } else {
                alert('Vui lòng nhập đủ thông tin.');
            }
        }

        function logout() {
            alert('Đăng xuất thành công');
            // Logic đăng xuất có thể là chuyển hướng hoặc xóa session
            location.reload(); // Tải lại trang
        }
    </script>

</body>
</html>
