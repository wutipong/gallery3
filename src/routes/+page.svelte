<script lang="ts">
	import {
		Breadcrumb,
		BreadcrumbItem,
		Card,
		CardBody,
		CardFooter,
		CardHeader,
		CardSubtitle,
		CardText,
		CardTitle,
		Collapse,
		Container,
		Dropdown,
		DropdownItem,
		DropdownMenu,
		DropdownToggle,
		Nav,
		NavItem,
		NavLink,
		Navbar,
		NavbarBrand,
		NavbarToggler,
		Row,
        Col,
        Badge,
        Icon
	} from 'sveltestrap';

	let isOpen = false;

	function handleUpdate(event) {
		isOpen = event.detail.isOpen;
	}
</script>
<div class="sticky-top">
<Navbar color="light" light expand="md">
	<NavbarBrand href="/">sveltestrap</NavbarBrand>
	<NavbarToggler on:click={() => (isOpen = !isOpen)} />
	<Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
		<Nav class="ms-auto" navbar>
			<NavItem>
				<NavLink href="#components/">Components</NavLink>
			</NavItem>
			<NavItem>
				<NavLink href="https://github.com/bestguy/sveltestrap">GitHub</NavLink>
			</NavItem>
			<Dropdown nav inNavbar>
				<DropdownToggle nav caret>Options</DropdownToggle>
				<DropdownMenu end>
					<DropdownItem>Option 1</DropdownItem>
					<DropdownItem>Option 2</DropdownItem>
					<DropdownItem divider />
					<DropdownItem>Reset</DropdownItem>
				</DropdownMenu>
			</Dropdown>
		</Nav>
	</Collapse>
</Navbar>

<Breadcrumb divider="/  ">
	<BreadcrumbItem>
		<a href="#home">&lt;root&gt;</a>
	</BreadcrumbItem>
	<BreadcrumbItem>
		<a href="#library">Library</a>
	</BreadcrumbItem>
	<BreadcrumbItem active>Data</BreadcrumbItem>
</Breadcrumb>
</div>

<Container>
	<h5>Directories</h5>
	<Container>
		<Row cols={{ lg: 5, md: 3, sm: 1 }}>
			{#each { length: 30 } as _, i}
            <Col>
				<Card class="mb-3">
					<CardHeader>
						<CardTitle>Card {i}</CardTitle>
					</CardHeader>
					<CardBody>
						<CardSubtitle>Card subtitle</CardSubtitle>
						<CardText>
							Some quick example text to build on the card title and make up the bulk of the card's
							content.
						</CardText>
					</CardBody>
					<CardFooter><Badge><Icon name="folder"/>&nbsp;Directory</Badge></CardFooter>
				</Card>
            </Col>
			{/each}
		</Row>
	</Container>
    <h5>Images</h5>
	<Container>
		<Row cols={{ lg: 5, md: 3, sm: 1 }}>
			{#each { length: 100 } as _, i}
            <Col>
				<Card class="mb-3">
					<CardHeader>
						<CardTitle>Card {i}</CardTitle>
					</CardHeader>
					<CardBody>
						<CardSubtitle>Card subtitle</CardSubtitle>
						<CardText>
							Some quick example text to build on the card title and make up the bulk of the card's
							content.
						</CardText>
					</CardBody>
					<CardFooter><Badge><Icon name="image"/>&nbsp;Images</Badge></CardFooter>
				</Card>
            </Col>
			{/each}
		</Row>
	</Container>
</Container>
