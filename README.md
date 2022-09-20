# User forms

This module creates the user related forms:
- user registration form
- user login form

## Usage

Once you installed the module you can use the atomic buiding blocks with [theme_render_rc](https://documentation.platformos.com/api-reference/liquid/platformos-tags#theme_render_rc) or a standard `render` tag.

In your project, you can render the component like this:

```
{% liquid
  assign form_params = '{}' | parse_json | hash_merge: action: '/do-login'
  theme_render_rc 'user-forms/organisms/login', params: form_params
%}
```

## Hooks

List of hooks provided and/or implemented by the module

## Examples

Code examples
