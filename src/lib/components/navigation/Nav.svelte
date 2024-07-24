<script lang="ts">
	import { AppRailTile, AppRailAnchor, AppRail } from '@skeletonlabs/skeleton';
	import { getDrawerStore } from '@skeletonlabs/skeleton';
	import VscodeIconsFileTypeSvelte from '~icons/vscode-icons/file-type-svelte';
	import VscodeIconsFileTypeTailwind from '~icons/vscode-icons/file-type-tailwind';
	import VscodeIconsFileTypePostcss from '~icons/vscode-icons/file-type-postcss';

	import IonHomeOutline from '~icons/ion/home-outline';

	const drawerStore = getDrawerStore();
	let currentTile: number = 0;

	function drawerClose(): void {
		drawerStore.close();
	}
</script>

<!-- <nav class="list-nav p-4">
	<ul>
		<li><a href="/" on:click={drawerClose}>Homepage</a></li>
		<li><a href="/about" on:click={drawerClose}>About</a></li>
		<li><a href="/blog" on:click={drawerClose}>Blog</a></li>
		<li><a href="/contact" on:click={drawerClose}>Contact</a></li>
	</ul>
</nav> -->
<AppRail>
	<svelte:fragment slot="lead">
		<AppRailAnchor href="/" regionLabel="flex justify-center items-center">
			<IonHomeOutline class="text-2xl" />
		</AppRailAnchor>
	</svelte:fragment>
	<!-- --- -->
	<AppRailTile
		regionLead="flex justify-center items-center"
		bind:group={currentTile}
		name="tile-1"
		value={0}
		title="tile-1"
	>
		<svelte:fragment slot="lead">
			<VscodeIconsFileTypeTailwind class="text-3xl" />
		</svelte:fragment>
		<span>Tile 1</span>
	</AppRailTile>

	<AppRailTile
		regionLead="flex justify-center items-center"
		bind:group={currentTile}
		name="tile-2"
		value={1}
		title="tile-2"
	>
		<svelte:fragment slot="lead">
			<VscodeIconsFileTypePostcss class="text-3xl" />
		</svelte:fragment>
		<span>Tile 2</span>
	</AppRailTile>

	<AppRailTile
		regionLead="flex justify-center items-center"
		bind:group={currentTile}
		name="tile-3"
		value={2}
		title="tile-3"
	>
		<svelte:fragment slot="lead">(icon)</svelte:fragment>
		<span>Tile 3</span>
	</AppRailTile>
	<!-- --- -->
	<svelte:fragment slot="trail">
		<AppRailAnchor
			regionLead="flex justify-center items-center"
			href="/"
			target="_blank"
			title="Account">(icon)</AppRailAnchor
		>
	</svelte:fragment>
</AppRail>
