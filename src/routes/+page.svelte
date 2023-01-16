<script context="module">
    import "../style/main.css";

    export async function load ({ fetch }) {
        const res = await fetch (
            `https://api.themoviedb.org/3/movie/popular?api_key={import.meta.env.VITE_API_KEY}&language=en-US&page=1`
        );
        const data = await res.json();
        if (res.ok) {
            return {
                props: { popular: data.results }
            }
        }
    }
</script>