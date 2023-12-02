# ff-repro
Attempts to reproduce https://bugzilla.mozilla.org/show_bug.cgi?id=1867816

This repo follows the basic setup for using tailwind w/ vite explained here: https://tailwindcss.com/docs/guides/vite

The only difference that causes the perf impact (afaict) is adding this line to `index.html`

```html
    <link rel="stylesheet" href="/src/index.css" />
```

Steps:
1. `npm i`
2. `npm run dev`
3. open up the dev tools and try to work w/ them to see a perf impact. My go-to test case was actually closing the dev tools while looking at the inspector pane which would cause the dev tools to hang for a few seconds before closing. It didn't happen every time, but usually after a refresh I would get that behavior. Sometimes I would also open up the network tab and do a refresh w/ `disable cache` enabled, although I'm not sure if that's relevant or not.
