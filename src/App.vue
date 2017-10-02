<template>

  <div class="shield course-finder">
    
    <!-- remove me later on from here !-->
    
    <h1 v-html="msg"></h1>
    <p>output bound data for testing:</p>
    <p>Selected level (this needs to be 'required'): {{ selectedLevel }}</p>
    <p>Search term: {{ searchString }}</p>
    <p>end test output</p>
    <hr />

    <!-- .to here !-->

    <div class="shield__content">
      <svg class="svg-icon " width="40px" height="40px">
        <use xlink:href="/media/svg/sprite.svg#icon-course-finder"></use>
      </svg>
      <h2>Find a course for you</h2>
      <form id="course-finder" method="get" action="/" class="">
        <div class="form__field floating-label">

          <select name="field-level" id="field-level" v-model="selectedLevel" required>
            <option value="" disabled selected>Study level</option>
            <option value="undergraduate">Undergraduate</option>
            <option value="postgraduate research">Postgraduate Research</option>
            <option value="postgraduate taught">Postgraduate Taught</option>
          </select>

          <label for="field-level">Study level</label>

        </div>
        <div class="form__field floating-label">

          <input v-model="searchString" name="field-search" id="field-search" type="text" placeholder="Enter a course title or keyword" />

          <label for="field-search">Keyword Search</label>

          <button role="button" type="submit" aria-label="Search Courses" aria-title="Search Courses" title="Search Courses" @click.prevent="kSearchMethod">

            <svg class="icon">
              <use xlink:href="/media/svg/sprite.svg#icon-search"></use>
            </svg>
          </button>
        </div>
      </form>
      <ul class="list-links">
        <li>
          <a href="#" class=" link-arrow">
            Undergraduate A-Z Courses
            <svg viewBox="0 0 16 16" width="16" height="16" class="icon-arrow">
              <path d="M7.2 12.73l-1.41-1.41 3.29-3.29-3.29-3.29L7.2 3.32l4.71 4.71-4.71 4.7z" />
            </svg>
          </a>
        </li>
        <li>
          <a href="#" class=" link-arrow">
            Postgraduate A-Z Courses
            <svg viewBox="0 0 16 16" width="16" height="16" class="icon-arrow">
              <path d="M7.2 12.73l-1.41-1.41 3.29-3.29-3.29-3.29L7.2 3.32l4.71 4.71-4.71 4.7z" />
            </svg>
          </a>
        </li>
        <li>
          <a href="#" class=" link-arrow">
            Book an Open Day
            <svg viewBox="0 0 16 16" width="16" height="16" class="icon-arrow">
              <path d="M7.2 12.73l-1.41-1.41 3.29-3.29-3.29-3.29L7.2 3.32l4.71 4.71-4.71 4.7z" />
            </svg>
          </a>
        </li>
        <li>
          <a href="#" class=" link-arrow">
            International Students
            <svg viewBox="0 0 16 16" width="16" height="16" class="icon-arrow">
              <path d="M7.2 12.73l-1.41-1.41 3.29-3.29-3.29-3.29L7.2 3.32l4.71 4.71-4.71 4.7z" />
            </svg>
          </a>
        </li>
      </ul>
    </div>
  </div>

</template>

<script>
export default {
  // name: 'app',
  data () {
    return {
      msg: 'Test data msg returned &#10004; <br /> Vue is running, &#127852;',
      searchString: '',  // initialised so that we can bind and use it on @click url if needed
      selectedLevel: '' // dropdown will change this. kSearchMethod will then pick it up in the url string below.
    }
  },
  methods: {
    kSearchMethod() {
      // console.log(this.searchString);
      window.location = 'https://www.keele.ac.uk/docs/alg-keele/?q=' + this.searchString + '&p=0&dFR%5BcourseLevelName%5D%5B0%5D=' + this.selectedLevel;
      // window.location = 'https://www.google.com';
    }
  }
}
</script>

<style lang="scss">
// #app {
//   font-family: 'Avenir', Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }

// h1, h2 {
//   font-weight: normal;
// }

// ul {
//   list-style-type: none;
//   padding: 0;
// }

// li {
//   display: inline-block;
//   margin: 0 10px;
// }

// a {
//   color: #42b983;
// }
</style>
