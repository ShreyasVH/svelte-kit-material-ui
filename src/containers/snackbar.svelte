<script>
    import Button from '@smui/button';
    import Snackbar, { Label, Actions } from '@smui/snackbar';
    import IconButton, { Icon } from '@smui/icon-button';
    import { onMount, onDestroy } from 'svelte';

    let type = '';
    let message = '';
    let snackbar;

    const handleShowSnackbar = event => {
        handleHideSnackbar();

        message = event.detail.message;
        type = event.detail.type;
        snackbar.open();
    };

    const handleHideSnackbar = () => {
        snackbar.close();
    };

    onMount(() => {
        window.addEventListener('show-snackbar', handleShowSnackbar);
        window.addEventListener('hide-snackbar', handleHideSnackbar);
    });

    onDestroy(() => {
        window.removeEventListener('show-snackbar', handleShowSnackbar);
        window.removeEventListener('hide-snackbar', handleHideSnackbar);
    });
    const showSnackbar = (event, data) => {
        console.log('event');
        event.preventDefault();

        const myEvent = new CustomEvent('show-snackbar', { detail: { type: data.type, message: data.message } });
        window.dispatchEvent(myEvent);
    };

    const hideSnackbar = () => {
        const myEvent = new CustomEvent('hide-snackbar', {});
        window.dispatchEvent(myEvent);
    };
</script>

<div>
    <Button variant="raised" onclick={(event) => showSnackbar(event, { message: 'Success', type: 'success' })}>
        Show Success
    </Button>
    &nbsp;
    <Button variant="raised" onclick={(event) => showSnackbar(event, { message: 'Error', type: 'error' })}>
        Show Error
    </Button>
    &nbsp;
    <Button variant="raised" onclick={(event) => showSnackbar(event, { message: 'Info', type: 'info' })}>
        Show Info
    </Button>
    &nbsp;
    <Button variant="raised" onclick={(event) => showSnackbar(event, { message: 'Warning', type: 'warning' })}>
        Show Warning
    </Button>

    <Snackbar bind:this={snackbar} class={type} timeoutMs={-1}>
        <Label>
            {message}
        </Label>
        <Actions>
            <IconButton title="Dismiss">
                <Icon class="material-icons">close</Icon>
            </IconButton>
        </Actions>
    </Snackbar>
</div>