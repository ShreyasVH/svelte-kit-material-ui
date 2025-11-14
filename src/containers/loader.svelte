<script>
    import Button from '@smui/button';
    import Dialog from '@smui/dialog';
    import CircularProgress from '@smui/circular-progress';

    let open = false;

    window.addEventListener('show-loader', function(event) {
        open = true;
    });

    window.addEventListener('hide-loader', function(event) {
        open = false;
    });

    const showLoader = (event) => {
        event.preventDefault();

        const myEvent = new CustomEvent('show-loader', {});
        window.dispatchEvent(myEvent);
    };

    const hideLoader = (event) => {
        event.preventDefault();

        const myEvent = new CustomEvent('hide-loader', {});
        window.dispatchEvent(myEvent);
    };
</script>

<div>
    <Button variant="raised" on:click={showLoader}>
        Show Loader
    </Button>

    <Dialog bind:open surface$style="background: transparent; box-shadow: none;" scrimClickAction="">
        <div tabindex="0">
            <CircularProgress style="height: 50px; width: 50px;" indeterminate />
        </div>
    </Dialog>
</div>