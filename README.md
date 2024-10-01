# SimpleIcons

## Usage

> [!IMPORTANT]\
> We ask that all users read our [legal disclaimer](https://github.com/simple-icons/simple-icons/blob/develop/DISCLAIMER.md) before using icons from Simple Icons.

### General Usage

Icons can be downloaded as SVGs directly from [our website](https://simpleicons.org/) - simply click the download button of the icon you want, and the download will start automatically.

### CDN Usage

Icons can be served from a CDN such as [jsDelivr](https://www.jsdelivr.com/package/npm/simple-icons) or [unpkg](https://unpkg.com/browse/simple-icons/). Simply use the `simple-icons` npm package and specify a version in the URL like the following:

```html
<img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@v13/icons/[ICON SLUG].svg" />
<img height="32" width="32" src="https://unpkg.com/simple-icons@v13/icons/[ICON SLUG].svg" />
```

Where `[ICON SLUG]` is replaced by the [slug] of the icon you want to use, for example:

```html
<img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@v13/icons/simpleicons.svg" />
<img height="32" width="32" src="https://unpkg.com/simple-icons@v13/icons/simpleicons.svg" />
```

These examples use the latest major version. This means you won't receive any updates following the next major release. You can use `@latest` instead to receive updates indefinitely. However, this will result in a `404` error if the icon is removed.

#### CDN with colors

We also provide a CDN service which allows you to use colors.

```html
<img height="32" width="32" src="https://cdn.simpleicons.org/[ICON SLUG]" />
<img height="32" width="32" src="https://cdn.simpleicons.org/[ICON SLUG]/[COLOR]" />
<img height="32" width="32" src="https://cdn.simpleicons.org/[ICON SLUG]/[COLOR]/[DARK_MODE_COLOR]" />
```

Where `[COLOR]` is optional, and can be replaced by the [hex colors](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color) or [CSS keywords](https://www.w3.org/wiki/CSS/Properties/color/keywords) of the icon you want to you use. The color is defaulted to the HEX color of the icon shown in [simpleicons.org website](https://simpleicons.org). `[DARK_MODE_COLOR]` is used for dark mode. The [CSS prefers-color-scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme) will be used when a value is specified. For example:

```html
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/gray" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/hotpink" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/0cf" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/0cf9" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/00ccff" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/00ccff99" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/orange/pink" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/_/eee" />
<img height="32" width="32" src="https://cdn.simpleicons.org/simpleicons/eee/_" />
```

You can use a `viewbox=auto` parameter to get a auto-sized viewbox. This is useful if you want all icons rendered with consistent size:

```html
<img height="20" src="https://cdn.simpleicons.org/github?viewbox=auto" />
<img height="20" src="https://cdn.simpleicons.org/simpleicons?viewbox=auto" />
<img height="20" src="https://cdn.simpleicons.org/awesomelists?viewbox=auto" />
```

### Node Usage <img src="https://cdn.simpleicons.org/nodedotjs/000/fff" alt="Node" align=left width=24>

The icons are also available through our npm package. To install, simply run:

```shell
npm install simple-icons
```

All icons are imported from a single file, where `[ICON SLUG]` is replaced by a capitalized [slug]. We highly recommend using a bundler that can tree shake such as [webpack](https://webpack.js.org/) to remove the unused icon code:
```javascript
// Import a specific icon by its slug as:
// import { si[ICON SLUG] } from 'simple-icons'

// For example:
// use import/esm to allow tree shaking
import { siSimpleicons } from 'simple-icons';
// or with require/cjs
const { siSimpleicons } = require('simple-icons');
```

It will return an icon object:

```javascript
console.log(siSimpleicons);

/*
{
    title: 'Simple Icons',
    slug: 'simpleicons',
    hex: '111111',
    source: 'https://simpleicons.org/',
    svg: '<svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>',
    path: 'M12 12v-1.5c-2.484 ...',
    guidelines: 'https://simpleicons.org/styleguide',
    license: {
        type: '...',
        url: 'https://example.com/'
    }
}

NOTE: the `guidelines` entry will be `undefined` if we do not yet have guidelines for the icon.
NOTE: the `license` entry will be `undefined` if we do not yet have license data for the icon.
*/
```

If you need to iterate over all icons, use:

```javascript
import * as icons from 'simple-icons';
```

#### TypeScript Usage <img src="https://cdn.simpleicons.org/typescript/000/fff" alt="Typescript" align=left width=19 height=19>

Type definitions are bundled with the package.

```typescript
import type { SimpleIcon } from 'simple-icons';
```

### PHP Usage <img src="https://cdn.simpleicons.org/php/000/fff" alt="Php" align=left width=24 height=24>

The icons are also available through our Packagist package. To install, simply run:

```shell
composer require simple-icons/simple-icons
```

The package can then be used as follows, where `[ICON SLUG]` is replaced by a [slug]:

```php
<?php
// Import a specific icon by its slug as:
echo file_get_contents('path/to/package/icons/[ICON SLUG].svg');

// For example:
echo file_get_contents('path/to/package/icons/simpleicons.svg');

// <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>
?>
```

