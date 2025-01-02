<script lang="ts">
    import type { Route, RouterOptions } from '@dvcol/svelte-simple-router';
    import { link, RouterContext, RouterView } from '@dvcol/svelte-simple-router';
    import Home from './routes/Home.svelte';
    import Test from './routes/Test.svelte';

    export const routes: Route[] = [
        {
            name: 'home',
            path: '/',
            component: Home,
        },
        {
            name: 'test',
            path: '/test/:id',
            component: Test,
        },
    ] as const;

    const options: RouterOptions = {
        routes,
        force: true,
        strict: true,
        hash: true
    } as const;
</script>

<RouterContext {options}>
    <a use:link href="/">Home</a>
    <a use:link href="/test/1">Test 1</a>
    <a use:link href="/test/2">Test 2</a>
    <RouterView></RouterView>
</RouterContext>
