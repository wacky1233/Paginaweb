# Paginaweb

Fitxer principal de la pagina web.

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

Aquest fitxer s'utilitza per fer la conexio a la base de dades. (per defecte estan configurades les credencials test i test123$).

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

Fitxer html de registre, ofereix inputs de nom,cognom,adreça i contrasenya per registrar usuaris.

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



```




