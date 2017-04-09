# lg-client-renderer reference

A Lagoon road extension that gives you renderer functionality on the client. This renderer does quick replacement and doesn't do virtual dom html difference changes. It should suffice for about 95% of all cases. When you start working more with a websocket pub/sub system you might want to consider writing your own renderer or use a virtual dom approach so user input will not get replaced on dom updates. Read more about writing extensions in the [guide](https://www.lagoonroad.com/guide).

| Information | - |
| ----------- | - |
| Code coverage | - |
| Repo link | [lr-client-renderer](https://github.com/lagoon-road/lr-client-renderer) |
| Dependencies | - |
| Size (Browserify, Babel, Uglify and Gzip)| 789 bytes |
| Version | 1.0.0 |
| License | MIT |
| Usage | [lagoonroad.com/guide](https://www.lagoonroad.com/guide) |

---

### Adding the extension to lagoon road

```
const router   = require('lg-client-renderer');
const core     = require('lr-core');
const road     = core('client')
  .extension('renderer', renderer, true);
```

---

### renderer.render(html, placeholder)
```
renderer.render('<section>...</section>', '.placeholderName');
```

_Prepare the component to be added to the template._

**html:string**  
The components html that you want to load.

**placeholder:string**  
A html selector that should be the parent of the html you want to add. The contents of the placeholder will be removed before adding the new html.

---

### renderer.html()
```
renderer.html();
```

_Replaces all the components that are added with `renderer.render` to the template at once. This way templates will only be added once even if they have been declared for replacement multiple times. _
