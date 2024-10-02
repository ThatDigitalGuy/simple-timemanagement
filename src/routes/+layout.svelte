<script lang="ts">
    import {
        Collapse,
        NavbarToggler,
        NavbarBrand,
        Nav,
        Navbar,
        NavItem,
        NavLink,
        Dropdown,
        DropdownToggle,
        DropdownMenu,
        DropdownItem,
        Container,
    } from "@sveltestrap/sveltestrap";

    let isOpen = false;

    function handleUpdate(event) {
        isOpen = event.detail.isOpen;
    }
</script>

<Navbar color="light" light expand="md" container="md">
    <NavbarBrand href="/">Time Management</NavbarBrand>
    <NavbarToggler on:click={() => (isOpen = !isOpen)} />
    <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
        <Nav class="ms-auto" navbar>
            <NavItem>
                <NavLink href="/">Log Hours</NavLink>
            </NavItem>
            <NavItem>
                <NavLink href="/history">History</NavLink>
            </NavItem>
            <NavItem>
                <NavLink href="/export">Export</NavLink>
            </NavItem>
        </Nav>
    </Collapse>
</Navbar>

<Container fluid>
    <slot />
</Container>
