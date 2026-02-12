<script>
    import Card, {
        Content,
        Actions,
        ActionButtons,
    } from '@smui/card';
    import Button, { Label } from '@smui/button';
    import LayoutGrid, { Cell } from '@smui/layout-grid';
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

    <br />

    <Card class="mdc-elevation--z12" style="max-width: 300px; text-align: center;">
        <Content class="mdc-typography--body2">
            <h2 class="mdc-typography--headline6" style="margin: 0;">
                Jack Kallis
            </h2>
            <h3
                    class="mdc-typography--subtitle2"
                    style="margin: 0 0 10px; color: #888;"
            >
                South Africa
            </h3>

            <img src="https://res.cloudinary.com/dyoxubvbg/image/upload/v1577106216/artists/default_m.jpg" height="200" width="200" style="margin-left: auto; margin-right: auto" />

            <div style="text-align: left">
                <LayoutGrid style="padding: 0">
                    <Cell span={6}>
                        <p>
                            <strong>Innings:</strong>
                            25
                        </p>

                        <p>
                            <strong>Runs:</strong>
                            25786
                        </p>

                        <p>
                            <strong>Balls:</strong>
                            25
                        </p>

                        <p>
                            <strong>Average:</strong>
                            45.46
                        </p>

                        <p>
                            <strong>Not Outs:</strong>
                            72
                        </p>

                        <p>
                            <strong>Highest: </strong>
                            172
                        </p>

                        <p>
                            <strong>50/100: </strong>
                            25/10
                        </p>
                    </Cell>

                    <Cell span={6}>
                        <p>
                            <strong>Catches</strong>
                            123
                        </p>

                        <p>
                            <strong>Wickets:</strong>
                            123
                        </p>

                        <p>
                            <strong>Balls: </strong>
                            12302
                        </p>

                        <p>
                            <strong>Runs: </strong>
                            12302
                        </p>

                        <p>
                            <strong>Fifers: </strong>
                            12
                        </p>

                        <p>
                            <strong>Economy: </strong>
                            7.85
                        </p>

                        <p>
                            <strong>DOB: </strong>
                            24/01/1967
                        </p>
                    </Cell>
                </LayoutGrid>
            </div>
        </Content>
    </Card>
</div>