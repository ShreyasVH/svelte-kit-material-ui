<script>
    import Tab, { Label } from '@smui/tab';
    import TabBar from '@smui/tab-bar';
    import Buttons from './buttons.svelte';
    import Table from './table.svelte';

    let tabNames = ['Buttons', 'Avatars', 'Chips', 'Table']
    let active = tabNames[0];
</script>

<TabBar tabs={tabNames} let:tab bind:active>
    <!-- Note: the `tab` property is required! -->
    <Tab {tab}>
        <Label>{tab}</Label>
    </Tab>
</TabBar>

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
{/if}