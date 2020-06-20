<footer class="pie-pagina">
    <section class="derechos">
        &copy; <span class="sitio-nombre">!Hi Anime 2020</span> - all rights reserved
    </section>
    <section class="condiciones">
        <ul>
            <li>
                <a href="#">Politicas de privacidad</a>
            </li>
            <li>
                <a href="#">Condiciones</a>
            </li>
            <li>
                <a href="#">
                    <img class="dev" src="assets/dev.png" />
                </a>
            </li>
        </ul>
    </section>
</footer>

<style>
    .pie-pagina {
        display: flex;
        justify-content: space-between;
        padding-left: 8px;
        align-items: center;
        height: 48px;
        background-color: #37474f;
        margin-top: 32px;
        overflow: hidden;
        position: fixed;
        bottom: 0;
        right: 0;
        left: 0;
    }

    .pie-pagina .derechos {
        color: white;
    }
    .pie-pagina .derechos .sitio-nombre {
        color: #ffcdd2;
    }

    .pie-pagina .condiciones ul {
        list-style: none;
        display: flex;
        align-items: center;
    }
    .pie-pagina .derechos, .pie-pagina .condiciones ul li {
        text-transform: uppercase;
        font-family: 'Roboto', sans-serif;
        font-size: 12px;
        font-weight: bold;
    }

    .pie-pagina .condiciones ul li {
        margin-right: 8px;
    }
    .pie-pagina .condiciones ul li a {
        text-decoration: none;
        color: white;
    }
    .pie-pagina .dev {
        width: 32px;
        height: 32px;
    }
</style>