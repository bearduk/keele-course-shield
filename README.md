# keele-course-shield

> Keele Course Shield Algolia search query

Binds the select box and search query and uses them to set the url triggered when pressing the button.

If you need to disable the button if no level is selected, you can do the following:

`<button role="button" type="submit" aria-label="Search Courses" aria-title="Search Courses" title="Search Courses" @click.prevent="kSearchMethod" :disabled="selectedLevel == 'requiredLevel'">`
and
`selectedLevel: 'requiredLevel'`


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).
