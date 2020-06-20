<script>
    import PublicationItem from './../components/publication-item.svelte';
    import { onMount, } from 'svelte';

    let publicaciones = [];

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

        }
        catch(e) {
            console.log(e);
        }
    }

    onMount(getDatos);
</script>

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
</style>
