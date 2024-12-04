<em> # Wsiaf Caballeros </em>
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inicio de Sesión</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f9;
        }

        .login-container {
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 300px;
        }

        .login-container h2 {
            text-align: center;
            margin-bottom: 20px;
        }

        .login-container input {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        .login-container button {
            width: 100%;
            padding: 10px;
            background-color: #003366;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .login-container button:hover {
            background-color: #0055aa;
        }
    </style>
</head>

<body>

    <div class="login-container">
        <h2>Iniciar Sesión</h2>
        <form id="loginForm">
            <input type="text" id="username" placeholder="Nombre de usuario" required>
            <input type="password" id="password" placeholder="Contraseña" required>
            <button type="submit">Iniciar sesión</button>
        </form>
    </div>

    <script>
        // Lista de usuarios válidos
        const validUsers = [
            { username: "tesoreromr", password: "1234" },
            { username: "secretariomr", password: "1234" },
            { username: "vivepresidentemr", password: "1234" },
            { username: "presidentemr", password: "1234" },
            { username: "asesormr", password: "1234" }
        ];

        // Evento para el formulario de inicio de sesión
        document.getElementById("loginForm").addEventListener("submit", function (e) {
            e.preventDefault();

            const username = document.getElementById("username").value;
            const password = document.getElementById("password").value;

            // Validar usuario y contraseña
            const user = validUsers.find(user => user.username === username && user.password === password);

            if (user) {
                // Guardar el nombre de usuario en localStorage
                localStorage.setItem("username", username);

                // Redirigir a inicio.html
                window.location.href = "inicio.html";
            } else {
                alert("Usuario o contraseña incorrectos.");
            }
        });
    </script>

</body>

</html>
