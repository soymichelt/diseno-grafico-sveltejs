<script>
    export let nombre;
    export let fecha;
    export let avatar;
    export let imagen;
</script>

<article class="publicacion">
    <div class="info">
        <img class="avatar" alt="{avatar}" src="{avatar}" />
        <h1>
            <span class="nombre">{nombre}</span>
            <span class="fecha">{fecha}</span>
        </h1>
    </div>
    <img class="image" alt="{imagen}" src="{imagen}" />
    <div class="accion">
        <button>Me gusta</button>
        <button>Compartir</button>
        <button>Denunciar</button>
    </div>
</article>

<style>
    .publicacion {
        max-width: 100%;
        margin: 8px;
        background-color: white;
        border-radius: 4px;
        box-shadow: 0px 2px 1px -1px rgba(0,0,0,0.2),
                    0px 3px 3px 0px rgba(0,0,0,0.14),
                    0px 4px 6px 0px rgba(0,0,0,0.12);
    }
    .publicacion .info {
        display: flex;
        flex-direction: row;
        height: 54px;
        padding: 11px 4px;
        box-sizing: border-box;
    }
    .publicacion .avatar {
        width: 32px;
        height: 32px;
        object-fit: cover;
        border-radius: 32px;
    }
    .publicacion .info h1 {
        margin: 3px 0px;
        line-height: 14px;
        margin-left: 6px;
    }
    .publicacion .info h1 .nombre {
        font-size: 12px;
        font-weight: 600;
        text-transform: uppercase;
        display: block;
    }
    .publicacion .info h1 .fecha {
        font-size: 10px;
        font-weight: 400;
        color: rgba(0,0,0,0.6);
    }

    .publicacion .image, .publicacion .nombre {
        max-width: 100%;
    }

    .publicacion .image {
        height: 231px;
        width: 100%;
        object-fit: cover;
    }

    .publicacion .accion {
        display: flex;
        padding: 4px;
    }
    .publicacion .accion button {
        flex: 1;
        height: 32px;
        background-color: transparent;
        border-radius: 4px;
        border:none;
        color: rgb(220, 0, 78);
        font-size: 12px;
        font-weight: 600;
        text-transform: uppercase;
    }
    .publicacion .accion button:hover {
        background-color: rgba(220, 0, 78, 0.08);
        cursor: pointer;
    }
</style>