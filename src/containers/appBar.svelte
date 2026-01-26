<script>
    import TopAppBar from '@smui/top-app-bar';
    import IconButton from '@smui/icon-button';

    import Drawer, {
        AppContent,
        Content,
        Header,
        Title,
        Subtitle,
      } from '@smui/drawer';

  import List, { Item, Text } from '@smui/list';

  let open = false;
</script>

<div class="flexy">
    <div class="drawer-container">
      <Drawer variant="dismissible" bind:open>
        <Header>
          <Title>Menu</Title>
          <Subtitle>Sub heading</Subtitle>
        </Header>
        <Content>
          <List>
            <Item
              href="javascript:void(0)"
            >
              <Text>Action 1</Text>
            </Item>
            <Item
              href="javascript:void(0)"
            >
              <Text>Action 2</Text>
            </Item>
          </List>
        </Content>
      </Drawer>

      <AppContent class="app-content">
        <main class="main-content flexy">
          <div class="top-app-bar-container flexor">
              <TopAppBar
                      variant="static"
                      color="primary"
              >
                  <IconButton class="material-icons" onclick={() => (open = !open)}>menu</IconButton>
              </TopAppBar>
          </div>
        </main>
      </AppContent>
    </div>



</div>
