# Formik Persist Values

<p>
  <a href="https://www.npmjs.com/package/formik-persist-values">
    <img height="20px" src="https://badgen.net/npm/license/formik-persist-values" />
  </a>
  <a href="https://www.npmjs.com/package/formik-persist-values">
    <img height="20px" src="https://badgen.net/npm/v/formik-persist-values" />
  </a>
  <a href="https://www.npmjs.com/package/formik-persist-values">
    <img height="20px" src="https://badgen.net/npm/dependents/formik-persist-values" />
  </a>
  <a href="https://www.npmjs.com/package/formik-persist-values">
    <img height="20px" src="https://badgen.net/npm/types/formik-persist-values" />
  </a>
  <a href="https://github.com/kolengri/formik-persist-values#readme">
    <img height="20px" src="https://badgen.net/github/issues/kolengri/formik-persist-values" />
  </a>
  <a href="https://bundlephobia.com/result?p=formik-persist-values">
    <img height="20px" src="https://badgen.net/bundlephobia/min/formik-persist-values" />
  </a>
  <a href="https://bundlephobia.com/result?p=formik-persist-values">
    <img height="20px" src="https://badgen.net/bundlephobia/minzip/formik-persist-values" />
  </a>
</p>

Persist and rehydrate a [Formik](https://github.com/jaredpalmer/formik) form values.

```
npm install formik-persist-values --save
```

```
yarn add formik-persist-values
```

# Basic Usage

Just import the `<PersistFormikValues >` component and put it inside any Formik form. It renders `null`!

```js
import React from 'react';
import { Formik, Field, Form } from 'formik';
import { PersistFormikValues } from 'formik-persist-values';

export const Signup = () => (
  <div>
    <h1>My Cool Persisted Values</h1>
    <Formik
      onSubmit={values => console.log(values)}
      initialValues={{ firstName: '', lastName: '', email: '' }}
    >
      {props => (
        <Form className="whatever">
          <Field name="firstName" placeholder="First Name" />
          <Field name="lastName" placeholder="Last Name" />
          <Field name="email" type="email" placeholder="Email Address" />
          <button type="submit">Submit</button>
          <PersistFormikValues name="signup-form" />
        </Form>
      )}
    </Formik>
  </div>
);
```

### Props

- `name: string`: LocalStorage key to save form state to.
- `ignoreValues:? string[]`: Provide array of keys if you need to do not persist some values.
- `debounce:? number`: Default is `300`. Number of ms to debounce the function that saves form state.
- `storage:? 'localStorage' | 'sessionStorage' | Storage`: default is `localStorage` . Send if you want Session storage or your own storage instead of Local storage.
- `persistInvalid:? boolean`: default is `false` . Persist if you want to save values while the form is invalid.
- `hashInitials:? boolean`: default is `false` . Hash initials values to prevent conflict between initialValues and persistedValues.
- `hashSpecificity:? number`: default is `7` . Hash initials values specificity to prevent conflict between cache hashes.

## Author

- Grigoriy Kolenko [@kolengri](https://twitter.com/kolengri)

## Inspired by

- Jared Palmer [@jaredpalmer](https://twitter.com/jaredpalmer)
- [formik-persist](https://github.com/jaredpalmer/formik-persist)

## Thanks

- Alex Kuchun [@kuchun](https://github.com/kuchun)
