<script>
  import themes from './themes.json'
  import Svg from './Svg.svelte'
  import Icon from './icon.svelte'

  let theme = ''
  let arrayThemes = Object.keys(themes).map((key) => ({ ...themes[key], type: key }))
</script>

<div class="p-sm-5 {themes[theme].plate}">
	<div class="card mb-4 mx-auto {themes[theme].plate}" style="max-width: 640px;">
		<div class="card-body">
			<div class="row">
				<div class="col-sm-auto text-center">
					<Icon />
				</div>
				<div class="col-sm text-center text-sm-end mt-4 mt-sm-0">
					<h1>Theme Universe</h1>
					<a class="btn {themes[theme].button}" href="https://www.zummon.page/" target="_blank">
						Made by zummon
					</a>
				</div>
			</div>
		</div>
	</div>
	<div class="row justify-content-center">
		<div class="col-sm-8 col-lg-6">
			<div class={themes[theme].svgcolor}>
				<Svg />
			</div>
			<div class="card {themes[theme].card}">
				<div class="card-body">
					<div class="row">
						<div class="col-sm">
							<h1>How does it work?</h1>
							<h4>Select one of the options to see</h4>
						</div>
						<div class="col-sm-auto">
							<select class="form-select form-select-lg" bind:value={theme} size={arrayThemes.length}>
                {#each arrayThemes as item}
                  <option value={item.type}>{item.name}</option>
                {/each}
							</select>
						</div>
					</div>
					<p class="mt-4">
						Lorem ipsum dolor sit amet consectetur adipisicing elit.
						Repellendus tempora possimus ullam tenetur atque temporibus,
						praesentium pariatur quibusdam sunt voluptate quaerat repellat,
						suscipit cum assumenda ea reiciendis accusantium debitis
						expedita!
					</p>
				</div>
			</div>
		</div>
	</div>
</div>