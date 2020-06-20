<script>
    import PublicationItem from './../components/publication-item.svelte';
    import { onMount, } from 'svelte';

    let publicaciones = [];
    let isLoading = true;

    async function getDatos() {
        try {
            const response = await fetch('https://rickandmortyapi.com/api/character/');
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
        <img src="/assets/loading.gif" />
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
        justify-content: center;
    }
</style>
