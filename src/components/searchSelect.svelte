<script>
    import Textfield from '@smui/textfield';

    let { onSelect } = $props();

    let search = $state('');
    let open = $state(false);
    let options = $state([]);

    const searchItems = async (keyword) => {
        let choices = [];
        if (keyword.length === 2) {
            choices = [
                'Apple',
                'Orange'
            ];
        } else if (keyword.length === 3) {
            choices = [
                'Banana',
                'Grapes'
            ];
        } else if (keyword.length === 4) {
            choices = [
                'Pomegranate'
            ];
        }

        return choices;
    }

    const handleChange = async (event) => {
        event.preventDefault();

        console.log(event.target.value);

        const keyword = event.target.value;
        if (keyword.length >= 2) {
            options = await searchItems(keyword);
            open = true;
        }
        search = keyword;
    };

    const handleSelect = (event, item) => {
        console.log(item);
        onSelect && onSelect(event, item);
        open = false;
        search = '';
    };
</script>

<div class="search-select">
    <Textfield class="mdc-text-field--focused" style="width: 100%" variant="outlined" bind:value={search} label="Search" oninput={handleChange} />

    {#if open}
        <div class="search-dropdown">
            {#each options as item}
                <button
                        type="button"
                        class="search-item"
                        onclick={(event) => handleSelect(event, item)}
                >
                    {item}
                </button>
            {/each}
        </div>
    {/if}
</div>

<style>
    .search-select {
        position: relative;
        width: 300px;
    }

    .search-dropdown {
        position: absolute;
        top: calc(100% + 4px);
        left: 0;
        right: 0;

        border-radius: 4px;

        max-height: 250px;
        overflow-y: auto;

        z-index: 1000;
    }

    .search-item {
        display: block;
        width: 100%;
        padding: 12px 16px;

        border: none;
        background: transparent;
        color: inherit;
        text-align: left;
        cursor: pointer;
    }

    .search-item:hover {
        background: rgba(128, 128, 128, 0.15);
    }
</style>