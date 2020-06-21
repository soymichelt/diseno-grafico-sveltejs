<header class="encabezado">
    <h1 class="logo"><span>!Hi</span> Anime</h1>
    <nav class="menu">
        <ul>
            <li>
                <a href="#">Inicio</a>
            </li>
            <li>
                <a href="#">Mi Perfil</a>
            </li>
            <li>
                <a href="#">Contacto</a>
            </li>
            <li>
                <a class="login" href="#">Iniciar Sesión</a>
            </li>
        </ul>
    </nav>
</header>

<style>
    .encabezado {
        background-color: #8f57fd;
        display: flex;
        justify-content: space-between;
        padding: 4px 8px;
        height: 56px;
        box-sizing: content-box;
        box-shadow: 0px 2px 4px -1px rgba(0,0,0,0.2),
                    0px 4px 5px 0px rgba(0,0,0,0.14),
                    0px 1px 10px 0px rgba(0,0,0,0.12);
        z-index: 1000;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        width: 100%;
    }
    .encabezado .menu ul {
        list-style: none;
        margin: 0;
        margin-right: 16px;
        height: 56px;
        line-height: 56px;
        box-sizing: border-box;
    }
    .encabezado .menu ul li {
        display: inline-block;
        line-height: 36px;
        height: 36px;
    }
    .encabezado .menu ul li a {
        display: block;
        height: 36px;
        box-sizing: border-box;
        padding: 0px 6px;
        padding-top: 2px;
        padding-bottom: 3px;
        text-decoration: none;
        text-transform: uppercase;
        color: white;
        font-weight: 500;
        font-size: 14px;
        border-radius: 4px;
    }
    .encabezado .menu ul li a:hover {
        background-color: rgba(0, 0, 0, 0.04);
    }

    .encabezado .login {
        box-sizing: content-box;
        height: 36px;
        background: linear-gradient(to right, #ef5350, #e53935);
        color: #FFFFFF;
        border-bottom: 3px solid #b71c1c;
    }

    .encabezado .logo {
        margin: 0;
        font-size: 24px;
        line-height: 56px;
        height: 56px;
        color: #fff;
    }
    .encabezado .logo span {
        color: #b71c1c;
        font-weight: bold;
    }
</style>