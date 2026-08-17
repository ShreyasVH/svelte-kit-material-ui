<script>
    import SearchSelect from '../components/searchSelect.svelte';

    let selectedItem = $state('');

    const handleSelect = (event, item) => {
        console.log(item);
        selectedItem = item;
    };
</script>

<div>
    <SearchSelect onSelect={handleSelect} />

    {selectedItem}
</div>