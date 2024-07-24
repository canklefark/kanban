<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppRail } from '@skeletonlabs/skeleton';
	import { initializeStores, Drawer, getDrawerStore } from '@skeletonlabs/skeleton';
	import Nav from '$lib/components/navigation/Nav.svelte';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	initializeStores();

	const drawerStore = getDrawerStore();
	function drawerOpen(): void {
		drawerStore.open({});
	}
</script>

<Drawer>
	<h2 class="p-4">Navigation</h2>
	<hr />
	<Nav />
</Drawer>
<!-- App Shell -->
<AppShell>
	<!-- App Bar -->
	<svelte:fragment slot="sidebarLeft">
		<Nav />
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
