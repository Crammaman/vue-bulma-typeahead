<template>
  <div id="demo">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Vue Bulma Typeahead Demo
          </h1>
        </div>
      </div>
    </section>

    <div class="container">

      <div class="columns">
        <div class="column is-4">
          <label class="label">U.S. State</label>
          <p class="control has-icons-left">
            <!-- Start Typeahead Component -->
            <typeahead :source="source1" :onSelect="onSelect1" :onChange="onChange1" :limit="5"></typeahead>
            <!-- End Typeahead Component -->
            <span class="icon is-small is-left">
              <i class="fa fa-magic"></i>
            </span>
          </p>
        </div>
          <div class="column is-4">
            <label class="label">U.S. State</label>
            <p class="control has-icons-left">
              <!-- Start Typeahead Component -->
              <typeahead :source="source2" :onSelect="onSelect2" :onChange="onChange2" :limit="5"></typeahead>
              <!-- End Typeahead Component -->
              <span class="icon is-small is-left">
                <i class="fa fa-magic"></i>
              </span>
            </p>
          </div>
      </div>

      <div class="columns">
        <div class="column is-4">
          You are searching for '{{ value1 }}'
        </div>
          <div class="column is-4">
            You are searching for '{{ value2 }}'
          </div>
      </div>

    </div>
  </div>
</template>

<script>
import Typeahead from './Typeahead.vue'

export default {
  name: 'demo',
  components: { Typeahead },
  data () {
    return {
      source1: ['Alabama', 'Alaska', 'Arizona', 'Arkansas', 'California',
      'Colorado', 'Connecticut', 'Delaware', 'Florida', 'Georgia', 'Hawaii',
      'Idaho', 'Illinois', 'Indiana', 'Iowa', 'Kansas', 'Kentucky', 'Louisiana',
      'Maine', 'Maryland', 'Massachusetts', 'Michigan', 'Minnesota', 'Mississippi',
      'Montana', 'Nebraska', 'Nevada', 'New Hampshire', 'New Jersey', 'New Mexico',
      'New York', 'North Carolina', 'North Dakota', 'Ohio', 'Oklahoma', 'Oregon',
      'Pennsylvania', 'Rhode Island', 'South Carolina', 'South Dakota', 'Tennessee',
      'Texas', 'Utah', 'Vermont', 'Virginia', 'Washington', 'West Virginia',
      'Wisconsin', 'Wyoming'],
        source2: ['Alabama', 'Alaska', 'Arizona', 'Arkansas', 'California',
        'Colorado', 'Connecticut', 'Delaware', 'Florida', 'Georgia', 'Hawaii',
        'Idaho', 'Illinois', 'Indiana', 'Iowa', 'Kansas', 'Kentucky', 'Louisiana',
        'Maine', 'Maryland', 'Massachusetts', 'Michigan', 'Minnesota', 'Mississippi',
        'Montana', 'Nebraska', 'Nevada', 'New Hampshire', 'New Jersey', 'New Mexico',
        'New York', 'North Carolina', 'North Dakota', 'Ohio', 'Oklahoma', 'Oregon',
        'Pennsylvania', 'Rhode Island', 'South Carolina', 'South Dakota', 'Tennessee',
        'Texas', 'Utah', 'Vermont', 'Virginia', 'Washington', 'West Virginia',
        'Wisconsin', 'Wyoming'],
      value1: '',
    value2: ''
    }
  },
  methods: {
    onSelect1 (value,name,index) {
      console.log(`'${value}', '${index}',  was selected.`)
      this.value = value
    },
    onChange1 (value,name,index) {
      console.log(`Value changed to ${value}.`)
      this.value = value
    },
    onSelect2 (value,name,index) {
      console.log(`'${value}', '${index}',  was selected.`)
      this.value = value
    },
    onChange2 (value,name,index) {
      console.log(`Value changed to ${value}.`)
      this.value = value
    }
  }
}
</script>

<style scoped>
.hero {
  margin-bottom: 35px;
}
</style>
