# Elegant Icons Sass

This is the Sass version of the [Elegant Themes](http://www.elegantthemes.com/)‘ [Elegant Icon Font](http://www.elegantthemes.com/blog/resources/elegant-icon-font).

## Installation

1. Install this package:

  ```bash
  npm install --save elegant-icons-sass
  ```

2. In your code, override the font path variable:

  ```scss
  $ei-font-path: '../assets/fonts/elegant-icons/';
  ```

  > Please note that the path above must be relative to  the generated `CSS` file, since it is used as a normal `src: url()` in an `@font-face` definition.

  > You might need to copy the font files yourself from the `node_modules/elegant-icons-sass/fonts` folder. You can use your build system of choice for that.

3. (Optionally) Override the default selector prefix:

  ```scss
  $ei-icon-prefix: 'my-prefix-';

  // Default value: 'ei-'
  ```

  > If you don‘t wish to use a prefix, set it to an empty string: `$ei-icon-prefix: '';`

  Check the [**Advanced Customization**](#Advanced-Customization) section below for more override options.

4. Import `elegant-icons-sass` in your code:

  ```scss
  @import 'node_modules/elegant-icons-sass/scss/elegant-icons-sass';
  ```

  Or, you can also add `node_modules/elegant-icons-sass/scss/` to your sass `includePaths` and make the import cleaner:

  ```scss
  @import 'elegant-icons-sass';
  ```

  > The import must be done **AFTER** the overrides of steps 2 and 3.

## Usage

To use the icons, you will need their names, which you can find [here](https://www.elegantthemes.com/blog/resources/elegant-icon-font) (right after the unicode reference list).

> The unicode references of the above list are meant to be used as `data-icon`, which the support has been removed in this sass version, because it‘s considered a bad practice due to performance issues. If you wish to use this way, you must define it yourself.

By default, the icon will be defined as a `::before` pseude-element. If you wish to change this default, check the [**Advanced Customization**](#Advanced-Customization) section below.

### As a mixin

Simply include the mixin in your selector:

```scss
.my-selector {
  @include elegant-icon('arrow_up');  
}
```

> When using as a mixin, the selector‘s `prefix` must **NOT** be used.

You can override the icon default placement by passing it a second parameter:

```scss
.my-selector {
  @include elegant-icon('social_twitter_circle', 'after');  
}
```

### As a placeholder

Simply extend the your selector with the placeholder:

```scss
.my-selector {
  @extend %ei-arrow_down;
}
```

> When using as a placeholder, the selector `prefix` must be used, unless you have overridden it as an empty string.

### As a class

If you just want to use it as a class, you can simply set the icon class name to your html element:

```html
<span class="ei-icon_plus"></span>
```

> When using as a class, the selector `prefix` must be used, unless you have overridden it as an empty string.

## Advanced Customization

You can override a few more variables:

1. The font file name:
  ```scss
  $ei-font-filename: 'my-custom-icons-filename';

  // Default value: 'ElegantIcons'
  ```

  > If you‘re just copying the font files and not renaming them, don‘t override this.

2. The font family name:
  ```scss
  $ei-font-family: 'My-Custom-Icons-Family-Name';

  // Default value: 'ElegantIcons'
  ```

  > Override only if you somehow wish to have a different font-family name defined to the icons font.

3. The default icon placement:
  ```scss
  $ei-default-placement: 'after';

  // Default value: 'before'
  ```

  > The icon placement can only be set as 'before' or 'after' which will define it as a `::before` or an `::after` pseudo-element, respectively.

## Contributing

1. Fork and Clone.

2. Install dependencies:

  ```bash
  npm install
  ```

3. Do your stuff!

4. Generate the css version by running:

  ```bash
  npm run build
  ```
5. Send PR.

## License

As per the original release, this icon font is dual licensed under the [GPL v2.0](http://www.gnu.org/licenses/gpl-2.0.html) and [MIT](http://opensource.org/licenses/MIT) license.
