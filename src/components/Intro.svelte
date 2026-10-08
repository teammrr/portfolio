<script lang="ts">
	let {
		name = 'Foo',
		nickname = '',
		title = '',
		summary = '',
		phone = '',
		email = '',
		github = '',
		linkedin = '',
		location = '',
		website = ''
	}: {
		name?: string;
		nickname?: string;
		title?: string;
		summary?: string;
		phone?: string;
		email?: string;
		github?: string;
		linkedin?: string;
		location?: string;
		website?: string;
	} = $props();
</script>

<div class="flex flex-wrap flex-row gap-x-4 text-sm sm:text-base print:text-[13px]">
	<div
		class="flex-1 min-w-0 basis-[45%] sm:basis-0 text-left sm:py-4 print:py-0 sm:w-48 break-words"
	>
		{#if phone}
			<p><a href={`tel:${phone}`}>{phone}</a></p>
		{/if}
		{#if email}
			<p><a href={`mailto:${email}`}>{email}</a></p>
		{/if}
		{#if location}
			<p>{location}</p>
		{/if}
	</div>

	<h2
		class="flex-none basis-full print:basis-full sm:basis-auto order-first sm:order-none print:order-first text-3xl sm:text-2xl md:text-3xl lg:text-6xl text-center px-0 py-2 sm:p-4 print:text-3xl print:pb-1 print:pt-0 break-words"
	>
		{name}
		<span class="block -mt-1 text-base lg:text-lg">({nickname})</span>
		{#if title}
			<span class="block mt-1 text-base sm:text-lg lg:text-xl font-semibold">{title}</span>
		{/if}
	</h2>

	<div
		class="flex-1 min-w-0 basis-[45%] sm:basis-0 text-right sm:py-4 print:py-0 sm:w-48 text-sm sm:text-base print:text-[13px] break-words print:text-right"
	>
		{#if github}
			<p>
				<a href={`https://github.com/${github}`} target="_blank" rel="noreferrer"
					>github.com/{github}</a
				>
			</p>
		{/if}
		{#if website}
			<p>
				<a href={`https://${website}`} target="_blank" rel="noreferrer">{website}</a>
			</p>
		{/if}
		{#if linkedin}
			<p>
				<a href={`https://linkedin.com/in/${linkedin}`} target="_blank" rel="noreferrer">LinkedIn</a
				>
			</p>
		{/if}
	</div>
</div>

{#if summary}
	<p class="text-left text-sm sm:text-base print:text-sm mb-2">{summary}</p>
{/if}

<style lang="postcss">
	a {
		text-decoration: underline;
	}
</style>
