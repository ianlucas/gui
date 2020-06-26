<template>
  <GuiFullscreen>
    <GuiTabs />
    <GuiSplit
      class="app-main"
      size="calc(100% - 40px)"
    >
      <GuiPanel :size="30">
        <GuiToolbar>
          <GuiSelect
            v-model="ambiente"
            :options="ambientes"
            placeholder="Ambiente"
          />
          <GuiButton>
            💾 Executar
          </GuiButton>
          <GuiLabel>
            ⚠️ Check your connection!
          </GuiLabel>
        </GuiToolbar>
      </GuiPanel>
      <GuiPanel
        class="scrollable"
        :size="70"
      >
        <img style="opacity: 0; width: 1920px; height: 1080px" src="https://i0.wp.com/www.farofeiros.com.br/wp-content/uploads/2017/01/Gabe-Newell-da-Steam-e1486861864816.jpg" />
        <img style="opacity: 0; width: 1920px; height: 1080px" src="https://i0.wp.com/www.farofeiros.com.br/wp-content/uploads/2017/01/Gabe-Newell-da-Steam-e1486861864816.jpg" />
      </GuiPanel>
    </GuiSplit>
  </GuiFullscreen>
</template>

<style>
.app-main .gutter {
  background-color: #f1f1f1;
}

.scrollable {
  overflow: scroll;
}
</style>

<script>
import GuiFullscreen from './components/GuiFullscreen'
import GuiTabs from './components/GuiTabs'
import GuiToolbar from './components/GuiToolbar'
import GuiSelect from './components/GuiSelect'
import GuiButton from './components/GuiButton'
import GuiPanel from './components/GuiPanel'
import GuiSplit from './components/GuiSplit'
import GuiLabel from './components/GuiLabel'

export default {
  components: {
    GuiFullscreen,
    GuiTabs,
    GuiToolbar,
    GuiSelect,
    GuiButton,
    GuiPanel,
    GuiSplit,
    GuiLabel
  },

  data: () => ({
    ambiente: '',
    ambientes: [
      {
        label: 'Desenvolvimento',
        value: 'DEV'
      },
      {
        label: 'Homologação',
        value: 'HML'
      }
    ]
  })
}
</script>
