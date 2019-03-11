# standard-package-flow-example

## 🤓 Install

```bash
npm i
```

## 🐛 Bug

### Steps to Reproduce

1. Run `npm run build`. It will fail.
2. Delete `src/shared/package.json`. It will succeed.

### More info

This problem is highlighted using `@babel/preset-flow`, but may be a more
general problem with how `.babelrc` is loaded (it may even be an issue with
Babel). It seems that whenever a `package.json` is encountered, the `.babelrc`
no longer applies.

However, it doesn’t seem that adding a `.babelrc` inside `src/shared` fixes it.
The same error occurs.

Also, to get this to run, `**/*.json` has to be ignored in the setup config.
