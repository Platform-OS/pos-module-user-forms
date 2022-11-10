# User forms

This module creates the user related forms:

- user registration form
- user login form

## Usage

Once you installed the module you can use the atomic buiding blocks with [theme_render_rc](https://documentation.platformos.com/api-reference/liquid/platformos-tags#theme_render_rc) or a standard `render` tag.

### Login component

In your project, you can render the login component like this:

```
{% liquid
  assign form_params = '{}' | parse_json | hash_merge: action: '/login', method: 'POST', redirect_to: '/welcome', errors: errors, values: values
  theme_render_rc 'user-forms/organisms/login', params: form_params
%}
```

You don't need to set `action`, `method` and `redirect_to` parameters, `action` will use [User module's](https://github.com/Platform-OS/pos-module-user) `POST /sessions/create` endpoint, the default `method` will be `POST` and the callback will redirect to the homepage by default.

`errors` and `values` are objects where the keys are the field names. `errors` values are slice of error messages and `values` values are field value strings.

### Registration component

In your project, you can render the register component like this:

```
{% liquid
  assign form_params = '{}' | parse_json | hash_merge: action: '/register', method: 'POST', redirect_to: '/welcome', errors: errors, values: values
  theme_render_rc 'user-forms/organisms/register', params: form_params
%}
```

You don't need to set `action`, `method` and `redirect_to` parameters, `action` will use [User module's](https://github.com/Platform-OS/pos-module-user) `POST /users/register` endpoint, the default `method` will be `POST` and the callback will redirect to the homepage by default.

`errors` and `values` are objects where the keys are the field names. `errors` values are slice of error messages and `values` values are field value strings.

## Hooks

List of hooks provided and/or implemented by the module

## Examples

Code examples

## Versioning

```
git fetch origin --tags
npm version major | minor | patch
```
