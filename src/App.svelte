<script>
  import themes from './themes.json'
  import Svg from './Svg.svelte'
  import Icon from './icon.svelte'

  let theme = ''
  let arrayThemes = Object.keys(themes).map((key) => ({ ...themes[key], type: key }))
</script>

<div class="sm:p-12 min-h-screen {themes[theme].plate}">
	<div class="mx-auto mb-4 flex flex-wrap gap-2 justify-center rounded-md border p-4" style="max-width: 640px;">
		<div class="text-center">
			<Icon />
		</div>
		<div class="grow text-right">
			<h1 class="mb-2 text-3xl font-medium xl:text-4xl">Theme Universe</h1>
			<a class="inline-block rounded-md border px-3 py-1.5 {themes[theme].button}" href="https://zummon.page/" target="_blank">
				Made by zummon
			</a>
		</div>
	</div>
	<div class="mx-auto {themes[theme].svgcolor}" style="max-width: 768px;">
		<Svg />
	</div>
	<div class="rounded-md p-4 mx-auto {themes[theme].card}" style="max-width: 640px;">
		<div class="flex flex-wrap gap-2">
			<div class="grow">
				<h1 class="mb-2 text-3xl font-medium xl:text-4xl">How does it work?</h1>
				<h4 class="text-lg font-medium xl:text-xl">Select one of the options to see</h4>
			</div>
			<div class="">
				<select class="rounded-md text-black text-lg" bind:value={theme} size={arrayThemes.length}>
					{#each arrayThemes as item}
						<option value={item.type}>{item.name}</option>
					{/each}
				</select>
			</div>
		</div>
		<p class="mt-2">
			Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Repellendus tempora possimus ullam tenetur atque temporibus,
			praesentium pariatur quibusdam sunt voluptate quaerat repellat,
			suscipit cum assumenda ea reiciendis accusantium debitis
			expedita!
		</p>
	</div>
</div>