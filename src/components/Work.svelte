<script lang="ts">
	import Hideable from './Hideable.svelte';

	let {
		position = '',
		company = '',
		url = '',
		years = [],
		details = []
	}: {
		position?: string;
		company?: string;
		url?: string;
		years?: string[];
		details?: string[];
	} = $props();
</script>

<div class="work-experience">
	<Hideable>
		<div
			class="work-header flex flex-col sm:flex-row print:flex-row sm:justify-between print:justify-between sm:gap-4 print:gap-4 font-bold mb-2 print:mb-0.5"
		>
			<div class="text-left">
				{position} · <a href={url} target="_blank" rel="noreferrer">{company}</a>
			</div>
			<div class="flex-none text-left sm:text-right print:text-right whitespace-nowrap">
				{years.join(' – ')}
			</div>
		</div>
		<ul class="text-left list-disc pl-5 sm:pl-8 print:pl-6">
			{#each details as detail (detail)}
				<Hideable>
					<li>
						{detail}
					</li>
				</Hideable>
			{/each}
		</ul>
	</Hideable>
</div>

<style lang="postcss">
	@reference "tailwindcss";

	.work-experience {
		@apply my-4;
	}

	a {
		text-decoration: underline;
	}

	@media print {
		.work-experience {
			@apply my-1;
		}

		li {
			break-inside: avoid;
		}

		.work-header {
			break-after: avoid;
		}
	}
</style>
