<div align="center">

<a href="https://laraform.io"><img src="assets/logo.svg" style="margin: 20px auto 10px" width="220"></a>

Reactive form builder for Vue.js with Laravel support

Create even the most complex forms with ease, using two-sided validation, <br> eloquent, nested elements, conditional logic, wizards and many more.


<a href="https://laraform.io"><img src="screenshots/screencast-1.gif" style="margin: 24px auto 24px" width="540"></a>

</div>

# Laraform Community Edition (Vue.js)

Laraform is a premium library aiming to become the world's best form builder tool for web developers. It enhances collaboration by standardizing the creation of forms and increases efficiency by eliminating tons of repetitive work. Laraform comes with a lighter "Community Edition" and a full version which can be purchased at our website.

## Features

Full features of Laraform:

* Two-sided validation
* 54 Laravel compatible frontend validators
* Eloquent ORM support
* Multiple file uploads
* 34+ built-in elements
* Nested elements
* Repeatable elements
* Translatable elements
* Conditional logic
* Form wizard
* Localization
* Theming
* Extensibility

## Examples

* [Shopify checkout clone](https://laraform.io/examples#shopify)
* [Login with backend support](https://laraform.io/examples#login)
* [Element examples](https://laraform.io/examples#elements)

## Browser Support

Laraform aims to support the latest versions of:

* Google Chrome
* Firefox
* Apple Safari
* Microsoft Edge
* Opera
* Internet Explorer 10+
* Safari iOS
* Chrome, Firefox and Default Browser Android

## Installation

Laraform is a full-stack library which comes with a separate frontend and backend library.

Install frontend library for Vue.js:

``` bash
npm i laraform --save
```

Install backend library for Laravel:

``` bash
composer require laraform/laraform-laravel
```

This will install Laraform's Community Edition. For the full package please [check out our website](https://laraform.io/pricing).

## Usage

Include javascript library:
``` javascript
import Vue from 'vue'
import Laraform from 'laraform'

Vue.use(Laraform)

const app = new Vue({
  el: '#app'
})
```

Import SCSS:
``` scss
@import '~laraform/src/themes/bs4/scss/theme.scss';
```

Create a form:

``` vue
// MyFirstForm.vue

<script>
  export default {
    mixins: [Laraform],
    data: () => ({
      schema: {
        hello_world: {
          type: 'text',
          label: 'Hello',
          default: 'World',
        }
      }
    })
  }
</script>
```

Add as a component and render:
``` html
<body>
  <div id="app">
    <my-first-form></my-first-form>
  </div>
</body>
```

#### Add Backend Support For Laravel

Publish config:

``` bash
php artisan vendor:publish
```

Choose **`Laraform\LaraformServiceProvider`**

Create a form:

``` php
// app/Forms/MyFirstForm.php

namespace App\Forms;

use Laraform;

class MyFirstForm extends Laraform
{
  public $schema = [
    'hello_world' => [
      'type' => 'text',
      'label' => 'Hello',
      'default' => 'World'
    ]
  ];
}
```

Pass the form to the view:
``` php
// routes/web.php

Route::get('/', function () {
  return view('welcome', [
    'form' => app('App\Forms\MyFirstForm')
  ]);
});
```

Render:
``` html
<!-- resources/views/welcome.blade.php --->

<html>
  <head>
    <!-- ... --->
    <meta name="csrf-token" content="{{ csrf_token() }}">
    <link rel="stylesheet" type="text/css" href="/css/app.css">
  </head>
  <body>
    <div id="app">
      {!! $form->render() !!}
    </div>

    <script src="/js/app.js"></script>
  </body>
</html>
```

Check out our docs for the full [Installation](https://laraform.io/docs/installation) and [Usage](https://laraform.io/docs/usage) guide.

## Documentation

A complete [Developer Guide](https://laraform.io/docs/rendering) and [API Reference](https://laraform.io/docs/api-laraform) is available at Laraform website.

## Issue Tracking

Laraform uses [GitHub Issues](/laraform/laraform/issue) for official bug tracking. Please follow our issue template to help us hunt down bugs as efficiently as possible.

## Support & Contribution

If you have any questions about Laraform or interested in contributing, please drop us a line at hello@laraform.io. We are happy for receiving feedbacks as well as growing our enthusiastic developer team.

## License

Laraform Community Edition comes with an MIT license so you are free to use this library in your projects. For the full version check out the licesne at [our website](https://laraform.io/pricing).