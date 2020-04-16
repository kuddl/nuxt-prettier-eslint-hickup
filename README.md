# Prettier Problem with nuxt

If you have a long style="" attribute in your HTML markup, 
prettier will format it to multiline

Link to "Source":
https://github.com/kuddl/nuxt-prettier-eslint-hickup/blob/38d0f56ac278233e0f69520302cd5ef8c78fbd55/pages/index.vue#L7

Link to "Generated Source":
https://github.com/kuddl/nuxt-prettier-eslint-hickup/blob/38d0f56ac278233e0f69520302cd5ef8c78fbd55/dist/index.html#L7


Before: 

```html
<h1 style="background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('/images/whateverimage-.jpg') no-repeat top center;background-size: cover;"> Title <h1>
```

After:
```html
<h1
  class="title"
  style="
    background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
      url('https://via.placeholder.com/400/e3000b/e3000b/?text=hidden.png')
        no-repeat top center;
    background-size: cover;
  "
>
  Title
</h1>
```

## Problem 1
If you run `npm run dev` the Styles are not "visible" since the browser will ignore it
-> 

## Problem 2 
if you run `npm run generate` the style will be stripped from the source code

## Prerequisites/Causes

-> the linting part is the `cause` with the new prettier 2.0
-> the "stripping" part is caused by NUXT (purgeCSS?) 




## Test Setup

```bash
# install dependencies
$ npm install

# serve it
$ npm run dev

# generate static project
$ npm run generate
```

