<script>
    import PublicationItem from './publication-list.svelte';
    import { onMount, } from 'svelte';

    let publicaciones = [];
    let isLoading = true;

    async function getDatos() {
        try {
            const response = await fetch('URL DE LA API REST');
            const { results } = await response.json();

            const publicacionesNuevas = [];
            results.map((item) => {
                publicacionesNuevas.push({
                    avatar: '/assets/dev.png',
                    nombre: item.name,
                    fecha: item.created,
                    imagen: item.image,
                });
            });
            publicaciones = publicacionesNuevas;
            isLoading = false;
        }
        catch(e) {
            console.log(e);
        }
    }

    onMount(getDatos);
</script>

{#if isLoading}
    <section class="loading">
        <h1>
            Espere un momento por favor...
        </h1>
        <img src="/assets/loading.gif" alt="Cargando..." />
    </section>
{/if}

<section class="publicaciones">
    {#each publicaciones as publicacion}
        <PublicationItem
            avatar={publicacion.avatar}
            nombre={publicacion.nombre}
            fecha={publicacion.fecha}
            imagen={publicacion.imagen}
        />
    {/each}
</section>

<style>
    .publicaciones {
        display: grid;
        grid-template-columns: 325px 325px 325px;
        justify-content: center;
    }
    .loading {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    h1 {
        color: #fff;
    }
    img {
        width: 48px;
        height: 48px;
    }
</style>
