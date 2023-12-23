<template> 
  <FormInput />
  <FormSelect />
  <FormTextarea />
  <FormCheckbox />
  <FormRadiobox />
  <FormToggles />
  <VButton />
  <DropdownButton />
  <GroupButtons direction="row" gap="5px" />
  <Accordion />
  <VLabel ff="'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif" />
  <ProgressBar />
  <VLabel @mouseover="active = true" @mouseout="active = false">For Tootlip</VLabel>
  <Tootlip width="300px" fz="14px" :active="active" />
  <message-box />
  <v-button @click="modal_active = !modal_active">For ModalWindow</v-button>
  <ModalWindow :active="modal_active" />
  <Alert />
  <ImageCarousel />
  <v-table />
  <v-list />
  <v-header />
  <v-footer />
  
</template>

<script>
  import FormInput from './components/FormInput.vue';
  import FormSelect from './components/FormSelect.vue';
  import FormTextarea from './components/FormTextarea.vue';
  import FormCheckbox from './components/FormCheckbox.vue';
  import FormRadiobox from './components/FormRadiobox.vue';
  import FormToggles from './components/FormToggles.vue';
  import VButton from './components/Buttons/VButton.vue';
  import DropdownButton from './components/Buttons/DropdownButton.vue';
  import GroupButtons from './components/GroupButtons.vue';
  import Accordion from './components/Accordion.vue';
  import VLabel from './components/Content/VLabel.vue'
  import ProgressBar from './components/Content/ProgressBar.vue'
  import Tootlip from './components/Content/Tootlip.vue'
  import MessageBox from './components/Content/MessageBox.vue'
  import ModalWindow from './components/Content/ModalWindow.vue'
  import Alert from './components/Content/Alert.vue'
  import ImageCarousel from './components/Content/ImageCarousel.vue'
  import VTable from './components/Content/VTable.vue'
  import VList from './components/Content/VList.vue'
  import VHeader from './components/Content/VHeader.vue'
  import VFooter from './components/Content/VFooter.vue'

  export default {
    components: {
      FormInput,
      FormSelect,
      FormTextarea,
      FormCheckbox,
      FormRadiobox,
      FormToggles,
      VButton,
      DropdownButton,
      GroupButtons,
      Accordion,
      VLabel,
      ProgressBar,
      Tootlip,
      MessageBox,
      ModalWindow,
      Alert,
      ImageCarousel,
      VTable,
      VList,
      VHeader,
      VFooter
    },
    data() {
      return {
        active: false,
        modal_active: false
      }
    }
  }
</script>

<style>
.scds {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
</style>