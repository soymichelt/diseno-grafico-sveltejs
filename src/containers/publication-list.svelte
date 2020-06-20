<script>
    import PublicationItem from './../components/publication-item.svelte';
    import { onMount, } from 'svelte';

    let publicaciones = [];

    async function getDatos() {
        try {
            const response = await fetch('https://kitsu.io/api/edge/anime');
            const { data } = await response.json();

            const publicacionesNuevas = [];
            data.map((item) => {
                publicacionesNuevas.push({
                    avatar: item.attributes.coverImage ? item.attributes.coverImage.original : '/assets/dev.png',
                    nombre: item.attributes.titles.en,
                    fecha: item.attributes.createdAt,
                    imagen: item.attributes.posterImage.original,
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
        /*grid-template-rows: 345px 345px;*/
        justify-content: center;
    }
</style>
