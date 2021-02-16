# rollup-plugin-shell-cycles

Execute shell command(s) sequentially or Synchronously at different lifecycle hooks.

```
npm i rollup-plugin-shell-cycles -D
```

## Examples

```javascript
// rollup.config.js
import shell from 'rollup-plugin-shell-cycles'

export default {
    entry: 'src/app.js',
    dest: 'public/app.js',
      plugins: [
        shell({
          buildStart: {
            commands: ['echo run my script'],
          },
          buildEnd: {
            commands: ['echo end my script'],
          },
          closeWatcher: {
            commands: ['echo close watcher'],
          },
          watchChange: {
            commands: ['echo watch change'],
          },
          moduleParsed: {
            commands: ['echo moduleParsed'],
          },
          generateBundle: {
            commands: ['echo generateBundle'],
          },
          renderError: {
            commands: ['echo render error'],
          },
          renderStart: {
            commands: ['echo render start'],
          },
          writeBundle: {
            commands: ['echo write bundle'],
          },
          transformIndexHtml: {
            commands: ['echo transform that html'],
          },
        })
    ]
}
```