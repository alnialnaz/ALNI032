<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login atau Daftar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center; /* Agar konten di tengah secara horizontal */
            padding: 20px;
        }

        .header {
            background: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            padding: 20px;
            width: 100%;
            max-width: 800px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            text-align: center;
            margin-bottom: 40px; /* Spasi agar form tidak bertumpuk */
        }

        .header h1 {
            color: #ff9305;
            margin: 0;
        }

        .header p {
            margin-top: 10px;
        }

        .content {
            background: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            padding: 40px;
            text-align: center;
            max-width: 400px;
            width: 100%;
        }

        .form-container {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        #form-title {
            margin-bottom: 20px;
            font-size: 24px;
            color: #333;
        }

        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }

        input[type="text"]:focus, input[type="password"]:focus {
            border-color: #ff9305;
            outline: none;
        }

        button {
            width: 100%;
            padding: 10px;
            background-color: #ff9305;
            border: none;
            border-radius: 4px;
            color: white;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background-color: #ff9305;
        }

        .switch-link {
            margin-top: 15px;
        }

        .switch-link a {
            color: #ff9305;
            text-decoration: none;
        }

        .switch-link a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <!-- Bagian Header (Selamat Datang) -->
    <div class="header">
        <h1>Selamat Datang di Pembelajaran Bilangan Bulat</h1>
        
    </div>

    <!-- Form Login/Daftar -->
    <div class="content">
        <div class="form-container">
            <h2 id="form-title">Login</h2>
            
            <!-- Form Login -->
            <form id="login-form" action="login.php" method="post">
                <input type="text" placeholder="Username" name="username" required><br>
                <input type="password" placeholder="Password" name="password" required><br>
                <button type="submit">Login</button>
            </form>

            <!-- Form Pendaftaran -->
            <form id="signup-form" style="display:none;" action="register.php" method="post">
                <input type="text" placeholder="Username" name="username" required><br>
                <input type="password" placeholder="Password" name="password" required><br>
                <button type="submit">Daftar</button>
            </form>

            <div class="switch-link">
                <span id="switch-text">Belum punya akun? <a href="javascript:void(0);" onclick="switchToSignup()">Daftar di sini</a></span>
            </div>
        </div>
    </div>

    <script>
        // Fungsi untuk berpindah ke form pendaftaran
        function switchToSignup() {
            document.getElementById("login-form").style.display = "none";
            document.getElementById("signup-form").style.display = "block";
            document.getElementById("form-title").innerText = "Daftar";
            document.getElementById("switch-text").innerHTML = 'Sudah punya akun? <a href="javascript:void(0);" onclick="switchToLogin()">Masuk di sini</a>';
        }

        // Fungsi untuk berpindah ke form login
        function switchToLogin() {
            document.getElementById("signup-form").style.display = "none";
            document.getElementById("login-form").style.display = "block";
            document.getElementById("form-title").innerText = "Login";
            document.getElementById("switch-text").innerHTML = 'Belum punya akun? <a href="javascript:void(0);" onclick="switchToSignup()">Daftar di sini</a>';
        }
    </script>
</body>
</html>
