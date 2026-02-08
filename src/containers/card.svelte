<script>
    import Card, {
        Content,
        Actions,
        ActionButtons,
    } from '@smui/card';
    import Button, { Label } from '@smui/button';
</script>

<div>
    <Card class="mdc-elevation--z12">
        <Content class="mdc-typography--body2">
            <h2 class="mdc-typography--headline6" style="margin: 0;">
                A card with media.
            </h2>
            <h3
                    class="mdc-typography--subtitle2"
                    style="margin: 0 0 10px; color: #888;"
            >
                And a subtitle.
            </h3>
            And higher elevation. It's all in this card. It's a veritable smorgasbord
            of card features.
        </Content>
        <Actions>
            <ActionButtons>
                <Button>
                    <Label>Action</Label>
                </Button>
                <Button>
                    <Label>Another</Label>
                </Button>
            </ActionButtons>
        </Actions>
    </Card>
</div>