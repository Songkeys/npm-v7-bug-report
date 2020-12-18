# npm-v7-bug-report

To reproduce this bug, run `npm i -g .` in this directory, which means to install this package globally.

## npm v6 behaviour

The install scripts are executed, therefore an error should be thrown since there is no command `ffffff`:

```
➜ npm i -g .

> npm-v7-bug@1.0.0 preinstall /Users/bytedance/.nvm/versions/node/v14.7.0/lib/node_modules/npm-v7-bug
> ffffff

sh: ffffff: command not found
npm ERR! code ELIFECYCLE
npm ERR! syscall spawn
npm ERR! file sh
npm ERR! errno ENOENT
npm ERR! npm-v7-bug@1.0.0 preinstall: `ffffff`
npm ERR! spawn ENOENT
npm ERR! 
npm ERR! Failed at the npm-v7-bug@1.0.0 preinstall script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/bytedance/.npm/_logs/2020-12-18T03_35_58_030Z-debug.log
```

## npm v7 behaviour

The install scripts are ignored. The package will be installed succefully:

```
➜ npm i -g .

up to date, audited 2 packages in 404ms

found 0 vulnerabilities
```