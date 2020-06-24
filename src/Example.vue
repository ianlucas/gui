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
        :size="70"
        :scrollable="true"
      >
        <img style="opacity: 0;" src="https://santacruzsolar.com.br/wp-content/uploads/2016/12/hd-beach-wallpapers-1080p.jpg" />
        <img style="opacity: 0;" src="https://santacruzsolar.com.br/wp-content/uploads/2016/12/hd-beach-wallpapers-1080p.jpg" />
      </GuiPanel>
    </GuiSplit>
  </GuiFullscreen>
</template>

<style>
.app-main .gutter {
  background-color: #f1f1f1;
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
