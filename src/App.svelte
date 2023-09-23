<script>
  import themes from './themes.json'
  import Svg from './Svg.svelte'
  import Icon from './icon.svelte'

  let theme = ''
  let arrayThemes = Object.keys(themes).map((key) => ({ ...themes[key], type:key }))
</script>

  <div class="sm:p-12 {themes[theme].plate}">
    <div
      class="flex flex-wrap items-center gap-2 rounded-md border mb-6 mx-auto p-4"
      style="max-width: 640px"
    >
      <div class="text-center">
        <Icon />
      </div>
      <div class="grow text-center sm:text-right mt-6 sm:mt-0">
        <h1 class="text-3xl mb-3 font-semibold">Theme Universe</h1>
        <a class="px-3 py-1.5 border rounded-md {themes[theme].button}" href="https://www.zummon.page/" target="_blank"> Made by zummon </a>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="col-sm-8 col-lg-6">
        <div class={themes[theme].svgcolor}>
          <Svg />
        </div>
        <div class="card {themes[theme].card}" >
          <div class="card-body">
            <div class="row">
              <div class="col-sm">
                <h1>How does it work?</h1>
                <h4>Select one of the options to see</h4>
              </div>
              <div class="col-sm-auto">
                <select
                  class="text-black"
                  size={arrayThemes.length}
                  bind:value={theme}
                >
                  {#each arrayThemes as item}
                    <option value={item.type}>
                      {item.name}
                    </option>
                  {/each }
                </select>
              </div>
            </div>
            <p class="mt-4">
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
              Repellendus tempora possimus ullam tenetur atque temporibus,
              praesentium pariatur quibusdam sunt voluptate quaerat repellat,
              suscipit cum assumenda ea reiciendis accusantium debitis expedita!
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>