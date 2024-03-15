# Paginaweb

El fitxer `index.html` es el fitxer principal de la pagina web. On els usuaris accediran per primer cop.

<details>
<summary>index.html</summary>
	
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fortisec | Hacking and CyberSecurity</title>
    <link rel="icon" type="image/x-icon" href="/IMAGES/fortisec.png">
    <link rel="stylesheet" href="fortisecpanel.css">
    <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
    <script src="https://unpkg.com/typed.js@2.0.16/dist/typed.umd.js"></script>

</head>
<body>

    <canvas id="matrixCanvas"></canvas>
                                                        <!-- Matrix -->

    <header class="header">
        <a href="#" class="logo">FORTISEC </a>

        <nav class="navbar">
            <a href="index.html" style="--i:1;" class="active">Home</a>
            <a href="/about/aboutus.html" style="--i:2;">About</a>
            <a href="#skill" style="--i:3;">Skills</a>
            <a href="/register/register.html" style="--i:4;">Sign Up</a>
            <a href="/login/login.html" style="--i:5;">Log In</a>
        </nav>
    </header>

    <section id="home" class="home">

        <div class="home-content" data-scroll data-scroll-speed="-5" >
            <h3 class="mu">Welcome to,</h3>
            <h1>FortiSec INC.</h1>
            <h3>Experts in  <span class="pro-text">
                <script>
                   var typed = new Typed(".pro-text", {
                      strings: [
                        "Security",
                        "Audits",
                        "Programming",
                        "Ethical Hacking",
                        "Pentesting",
                      ],
                      typeSpeed: 100,   
                      backSpeed: 100,   
                      backDelay: 1000,  
                      loop: true        
                    });
                </script>
            </span></h3>
            
            <p>We are a company that is dedicated to programming and cybersecurity.<br>
            <br>Here you can apply your skills to show people how good you are at this!<br><br>
            Have fun!! :)
            </p>

            <div class="home-sci">
                <a href="mailto:fortisec.inc.smx@gmail.com" target="_blank"><i class='bx bxl-gmail'></i></a>
                <a href="https://www.linkedin.com/in/fortisec-inc-a855032b3/" target="_blank"><i class='bx bxl-linkedin' ></i></a>
                <a href="https://www.instagram.com/fortisec.inc/" target="_blank"><i class='bx bxl-instagram'></i></a>
            </div>
           <a href="/register" class="btn-box">Join Now</a>

        </div>

        <div class="home-img">
            <img src="/IMAGES/fortisec.png" alt="Descripción de la imagen">
            <div class="glowing-circle">
                <span></span>
                <span></span>
                <div class="image">
                    <img src="" alt="">
                </div>
            </div>
        </div>

    </section>

</body> 
</html>
```
</details>

Aquest fitxer s'utilitza per fer la conexio a la base de dades. (per defecte estan configurades les credencials test i test123$).

<details>
<summary>db.php</summary>

```php
<?php
$servername = "localhost";
$username = "test";
$password = "test123$";
$dbname = "fortisec";

$conexion = new mysqli($servername, $username, $password, $dbname);

if ($conexion->connect_error) {
    die("Conexión fallida: " . $conexion->connect_error);
}
?>
```
</details>

Fitxer html de registre, ofereix inputs de nom,cognom,adreça i contrasenya per registrar usuaris.

<details>

<summary>register.html</summary>

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign Up - FortiSec</title>
    <link rel="stylesheet" type="text/css" href="../CSS/register-styles.css">
    <link rel="shortcut icon" href="favicon.png" type="image/png">
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&amp;display=swap" rel="stylesheet">
</head>

<body>
    <center>
        <div class="container">
            <div class="form-container">
                <form name="frmRegister" id="frmRegister" method="post" enctype="multipart/form-data">
                    <img class="logo" src="../IMAGES/fortisec.png" alt="test">
                    <h1 class="tunning">FORTISEC</h1>
                    <div class="input-row">
                        <span id="lastName-info" class="info"></span><br />
                        <input placeholder="Username" type="text" class="input-field" name="username" id="username" required/>
                    </div>
                    <div class="input-row">
                        <span id="email-info" class="info"></span><br />
                        <input placeholder="Email" type="email" class="input-field" name="email" id="email" required/>
                    </div>
                    <div class="input-row">
                        <span id="password-info1" class="info"></span><br />
                        <input placeholder="Password" type="password" class="input-field" name="password" id="password" required/>
                    </div>
                    <div class="input-row">
                        <span id="password-info2" class="info"></span><br />
                        <input placeholder="Repeat password" type="password" class="input-field" name="repeat-password" id="repeat-password" oninput="checkPasswordMatch()" required/>
			<a onclick="goBack()" style="margin-left: -278px; margin-top: 61px; color: #959595; position: absolute; font-size: 10px; font-family: 'Varela Round'; text-decoration: none;">&lt;&lt; BACK</a>
                        <a href="../index.html" style="margin-left: -39px; margin-top: 61px; color: #959595; font-family: auto; position: absolute; font-size: 10px; font-family: 'Varela Round'; text-decoration: none;">HOME</a>
                    </div>
                    <div>
                        <input type="submit" id="rbutton_" name="send" class="btn-submit" value="SIGN UP" onclick="registrarUsuario()"/>
                        <div id="statusMessage" style="color: #d30000; font-family: 'Varela Round'; font-size: 13px; margin-top: -39px; padding: 15px;"></div>
                        <div class="registrationFormAlert" style="color:green;" id="CheckPasswordMatch">
                    </div>
                    <div class="button-signup">
                        <p id="message">Already have an account?</p><button class="mi-boton" type="button" onclick="window.location.href='../login/'">Log In</button>
                    </div>
                    <script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>
                    <script src="js/validaciones.js"></script>
                    <script src="js/registro.js"></script>
                </form>
            </div>
        </div>
    </center>
    <script src="../JAVASCRIPT/back.js"></script>
</body>
</html>
```
</details>

El fitxer `funcions.php` és utilitzat per definir les funcions de registrar l'usuari a la BD i verificar si l'usuari existeix en la BD. Aquestes funcions es faran servir quan l'usuari intenti iniciar sessió o crear un nou usuari. Es fan servir consultes parametritzades per evitar injeccions SQL.

<details>
<summary>funciones.php</summary>

```php
<?php
include('db.php');

function registrarUsuario($username, $password, $email) {
    global $conexion;

    if (existeUsuario($username)) {
        return false;
    }

    $hashedPassword = password_hash($password, PASSWORD_DEFAULT);

    $stmt = $conexion->prepare("INSERT INTO usuarios (username, password, email) VALUES (?, ?, ?)");
    $stmt->bind_param("sss", $username, $hashedPassword, $email);

    if ($stmt->execute()) {
        return true;
    } else {
        return false;
    }

    $stmt->close();
}

function existeUsuario($username) {
    global $conexion;

    $stmt = $conexion->prepare("SELECT COUNT(*) FROM usuarios WHERE username = ?");
    $stmt->bind_param("s", $username);

    $stmt->execute();
    $stmt->bind_result($count);
    $stmt->fetch();

    return $count > 0;

    $stmt->close();
}

function iniciarSesion($username, $password) {
    global $conexion;

    $stmt = $conexion->prepare("SELECT id, username, password FROM usuarios WHERE username = ?");
    $stmt->bind_param("s", $username);

    $stmt->execute();
    $stmt->bind_result($id, $storedUsername, $storedPassword);
    $stmt->fetch();

    $stmt->close();

    if ($storedUsername && password_verify($password, $storedPassword)) {
        session_start();

        $_SESSION['user_id'] = $id;
        $_SESSION['username'] = $storedUsername;

        return true;
    }

    return false;
}
?>
```
</details>

El fitxer 'register.php' s'utilitza per connectar-se a la BD i registrar l'usuari, email i contrasenya en la BD mitjançant la funció 'registrarUsuario()'. També s'encarrega de verificar si el formulari de registre s'ha enviat correctament.

<details>
<summary>register.php</summary>

```php
<?php
include('../includes/db.php');
include('../includes/funciones.php');

$response = array(); // Inicializar la variable de respuesta

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Este bloque se ejecuta si el formulario ha sido enviado (método POST)
    $username = $_POST['username'];
    $email = $_POST['email'];
    $password = $_POST['password'];

    // Llamar a la función para registrar el usuario
    if (registrarUsuario($username, $password, $email)) {
        $response['status'] = 'success';
        $response['message'] = 'Registro exitoso.';
        header("Location: /login/");
        exit();
    } else {
        $message = "Error al iniciar sesión. Verifica tus credenciales.";
        $response['status'] = 'error';
        $response['message'] = 'Error al registrar el usuario. El nombre de usuario o email ya existe.';
    }

    // Devolver la respuesta como JSON
    header('Content-Type: application/json');
    echo json_encode($response);
}
?>
```
</details>

Aquest fitxer defineix els estils del panell de registre d'usuaris.

<details>
<summary>register-styles.css</summary>

```css
@import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro&family=Varela+Round&display=swap');
:root {
    color-scheme: dark;
}

#statusMessage {
    color: #d30000;
    font-family: 'Varela Round';
    font-size: 13px;
    margin-top: -39px;
    padding: 19px;

}

.logo {
    width: 63px;
    height: auto;
    margin-top: 40px;
    margin-left: 31px;
}

.mi-boton {
  background: transparent;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 12px;
  font-family: 'Varela Round';
}

.mi-boton:hover {
  color: #b3b3b3;
}

.mi-boton:focus {
    outline: none;
}

body {
    background: #212121;
    text-align: center;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

h1 {
    font-size: 30px;
    font-weight: 500;
    font-family: Tahoma, Geneva;
    margin-bottom: 10px;
    color: #ddd;
    background: transparent;
}

.tunning {
    font-size: 30px !important;
    font-weight: 400 !important;
    line-height: calc(24px + 1.5vw) !important;
    color: white !important;
    font-family: 'Press Start 2P', cursive;
    text-shadow: 0 3px 0 #7e7676;
    background: transparent;
}

.container {
    background: #242424;
    border: 1px solid #242424;
    border-radius: 10px;
    padding: 1px;
    margin: 175px auto 50px;
    max-width: 364px;
    height: 665px; /* Ajustado para acomodar el formulario de registro */
    box-shadow: 8px 0 10px rgba(0, 0, 0, 0.3);
}

#message {
  display: inline;
  margin-left: -82px;
  font-size: 12px;
  font-family: 'Varela Round';
}

input {
    background: #1c1c1c;
    border-bottom: 3px solid #343434;
    border-left: 1px solid #373737ad;
    border-right: 1px solid #2f2f2f;
    border-top: 1px solid #0000;
    padding: 4px 15px 2px 17px;
    margin-bottom: 10px;
    font-weight: 400;
    font-family: 'Varela Round';
    width: 249px;
    height: 29px;
    color: #717171;
    border-radius: 3px;
    display: inline-block;
    user-select: none;
}

input::placeholder {
    color: #999;
}

input:focus {
    outline: none;
    border-bottom: 3px solid #343434;
    border-left: 1px solid #343434;
    border-right: 1px solid #343434;
    border-top: 1px solid #343434;
}

.btn-submit {
    width: 283px;
    height: 36px;
    position: relative;
    display: inline-block;
    border: 0.01px solid rgba(77, 77, 77, 0.59);
    border-radius: 8px;
    color: #fff;
    font-family: 'Varela Round';
    font-size: .875rem;
    font-weight: 600;
    line-height: 2px;
    box-shadow: inset 0 1px 3px rgba(87, 87, 87, 0.1), 0 1px 0 rgba(255, 255, 255, .075);
    cursor: pointer;
    user-select: none;
    transition: 7.3s;
    margin: 46px 5px;
    background-color: #373737;
}

.btn-submit:focus {
    outline: none;
}

.btn-submit:active {
    color: white;
    background: linear-gradient(180deg, #191717, #282727) !important;
}

.btn-submit:hover {
    color: white;
    background: linear-gradient(180deg, #717171, #5b5b5b);
}
```
</details>

Aquest fitxer defineix els estils del panell d'inici de sesio del usuari.

<details>
	
<summary>login-styles.css</summary>
	
```css
@import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro&family=Varela+Round&display=swap');
:root {
    color-scheme: dark;
}

.logo {
width: 63px;
height: auto;
margin-top: 40px;
margin-left: 31px;
}

.mi-boton {
  background: transparent;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 12px;
  font-family: 'Varela Round';
}

.mi-boton:hover {
  color: #b3b3b3;
}

.mi-boton:focus {
    outline: none;
}


body {
    background: #212121;
    text-align: center;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

h1 {
    font-size: 30px;
    font-weight: 500;
    font-family: Tahoma, Geneva;
    margin-bottom: 10px;
    color: #ddd;
    background: #212121;
    background: transparent;
}

.tunning {
    font-size: 30px !important;
    font-weight: 400 !important;
    line-height: calc(24px + 1.5vw) !important;
    color: white !important;
    font-family: 'Press Start 2P', cursive;
    text-shadow: 0 3px 0 #7e7676;
    background: transparent;
}

#message {
  display: inline;
  margin-left: -112px;
  font-size: 12px;
  font-family: 'Varela Round';
}

.container {
background: #242424;
border: 1px solid #242424;
border-radius: 10px;
padding: 1px;
margin: 175px auto 50px;
max-width: 364px;
height: 547px;
box-shadow: 8px 0 10px rgba(0, 0, 0, 0.3);
}

input {
  background: #1c1c1c;
  border-bottom: 3px solid #343434;
  border-left: 1px solid #373737ad;
  border-right: 1px solid #2f2f2f;
  border-top: 1px solid #0000;
  padding: 4px 15px 2px 17px;
  margin-bottom: 10px;
  font-weight: 400;
  font-family: Tahoma;
  width: 249px;
  height: 29px;
  color: #717171;
  border-radius: 3px;
  display: inline-block;
  user-select: none;
}

input::placeholder {
    color: #999;
}

input:focus {
    outline: none;
    border-bottom: 3px solid #343434;
    border-left: 1px solid #343434;
    border-right: 1px solid #343434;
    border-top: 1px solid #343434;
}

input {
  background: #1c1c1c;
  border-bottom: 3px solid #343434;
  border-left: 1px solid #373737ad;
  border-right: 1px solid #2f2f2f;
  border-top: 1px solid #0000;
  padding: 4px 15px 2px 17px;
  margin-bottom: 10px;
  font-weight: 400;
  font-family: 'Varela Round';
  width: 249px;
  height: 29px;
  color: #717171;
  border-radius: 3px;
  display: inline-block;
  user-select: none;
}

input::placeholder {
    color: #999;
}

input:focus {
    outline: none;
    border-bottom: 3px solid #343434;
    border-left: 1px solid #343434;
    border-right: 1px solid #343434;
    border-top: 1px solid #343434;
}

.btn-submit {
    width: 283px;
height: 36px;
position: relative;
display: inline-block;
border: 0.01px solid rgba(77, 77, 77, 0.59);
border-radius: 8px;
color: #fff;
font-family: 'Varela Round';
font-size: .875rem;
font-weight: 600;
line-height: 2px;
box-shadow: inset 0 1px 3px rgba(87, 87, 87, 0.1), 0 1px 0 rgba(255, 255, 255, .075);
cursor: pointer;
user-select: none;
transition: 7.3s;
margin: 46px 5px;
background-color: #373737;
}

.disabled {
    filter: brightness(50%);
    pointer-events: none;
}

.btn-submit:focus {
    outline: none;
}

.btn-submit:active {
    color: white;
    background: linear-gradient(180deg, #191717, #282727) !important;
}

.btn-submit:hover {
    color: white;
    background: linear-gradient(180deg, #717171, #5b5b5b);
}

p {
    color: #959595;
    font-family: Tahoma;
    font-size: 12px;
}

.homedos {

margin-left: 99px;
    margin-top: -43px;
    color: #959595;
    font-family: auto;
    position: absolute;
    font-size: 10px;
    font-family: 'Varela Round';
    text-decoration: none;

}

a {
margin-left: -135px;
    margin-top: -43px;
    color: #959595;
    font-family: auto;
    position: absolute;
    font-size: 10px;
    font-family: 'Varela Round';
    text-decoration: none;
}
```
</details>

</details>

Aquest fitxer defineix els estils del panell d'inici de sesio del usuari.

<details>
	
<summary>login-styles.css</summary>








