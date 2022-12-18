# reproduce-volar-syntax-highlight-bug

![screenshot](screenshot.jpg)

## Environments

- OS: MacOS BigSur 11.7
- volar: v1.0.13
- vscode:

  ```txt
  Version: 1.74.0 (Universal)
  Commit: 5235c6bb189b60b01b1f49062f4ffa42384f8c91
  Date: 2022-12-05T16:43:37.594Z
  Electron: 19.1.8
  Chromium: 102.0.5005.167
  Node.js: 16.14.2
  V8: 10.2.154.15-electron.0
  OS: Darwin x64 20.6.0
  ```

## Reproduce steps

1. Clone it and install [volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)
2. Run `Volar (Debug): Write Virtual Files` command
3. Disable Volar Extension in the workspace and reload vscode
4. Inspect `src/Hello/World/World.vue.js` & `src/Bye/World/World.vue.js`

## Some observations

1. remove jsconfig.json can mitigate

2. modified `name` or`version` or `main` of `package.json` following

```diff
{
- "name": "World",
+ "name": "World2",
  "version": "0.0.0",
  "private": true,
  "main": "./World.vue"
}
```

then the syntax highlight will be fine.

## Expected

- [ ] syntax highlight should be correct in every `.vue`
- [ ] find `.vue` path if import folder path from `App.vue` with alias in `jsconfig.json`
- [ ] the type of components in `App.vue` `components` can not be `any`

## Related discussions

- [johnsoncodehk/volar#2200](https://github.com/johnsoncodehk/volar/issues/2200)
- [https://t.me/typescript_zh/65081](https://t.me/typescript_zh/65081)
  - [video](demo.mp4)
