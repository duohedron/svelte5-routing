<script>
    import { useRoute } from '@dvcol/svelte-simple-router/router';

    const router = useRoute();
    const params = router.location?.params;

    const id = params?.id;
</script>

<h1>Test</h1>
<p>{id}</p>
