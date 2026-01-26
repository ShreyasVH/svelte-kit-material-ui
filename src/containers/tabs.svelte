<script>
    import Tab, { Label } from '@smui/tab';
    import TabBar from '@smui/tab-bar';
    import Buttons from './buttons.svelte';
    import Table from './table.svelte';
    import Loader from './loader.svelte';

    let tabNames = ['Buttons', 'Avatars', 'Chips', 'Table', 'Loader']
    let active = tabNames[0];
</script>

<TabBar tabs={tabNames} bind:active>
    <!-- Note: the `tab` property is required! -->
    {#snippet tab(tab)}
        <Tab {tab}>
            <Label>{tab}</Label>
        </Tab>
    {/snippet}
</TabBar>

<div style="padding: 0 5%">
    {#if active === 'Buttons'}
        <div>
            <Buttons />
        </div>
    {:else if active === 'Avatars'}
        <div>
            Avatars
        </div>
    {:else if active === 'Table'}
        <div>
            <Table />
        </div>
    {:else if active === 'Loader'}
        <div>
            <Loader />
        </div>
    {/if}
</div>
