# api documentation for  [del (v2.2.2)](https://github.com/sindresorhus/del#readme)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-del.svg)](https://travis-ci.org/npmdoc/node-npmdoc-del)
#### Delete files and folders

[![NPM](https://nodei.co/npm/del.png?downloads=true)](https://www.npmjs.com/package/del)

[![apidoc](https://npmdoc.github.io/node-npmdoc-del/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-del_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-del/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-del/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "author": {
        "name": "Sindre Sorhus",
        "email": "sindresorhus@gmail.com",
        "url": "sindresorhus.com"
    },
    "bugs": {
        "url": "https://github.com/sindresorhus/del/issues"
    },
    "dependencies": {
        "globby": "^5.0.0",
        "is-path-cwd": "^1.0.0",
        "is-path-in-cwd": "^1.0.0",
        "object-assign": "^4.0.1",
        "pify": "^2.0.0",
        "pinkie-promise": "^2.0.0",
        "rimraf": "^2.2.8"
    },
    "description": "Delete files and folders",
    "devDependencies": {
        "ava": "*",
        "fs-extra": "^0.30.0",
        "path-exists": "^2.0.0",
        "tempfile": "^1.1.1",
        "xo": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "c12c981d067846c84bcaf862cff930d907ffd1a8",
        "tarball": "https://registry.npmjs.org/del/-/del-2.2.2.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "files": [
        "index.js"
    ],
    "gitHead": "3a97a5ba131055fbf7eb39f5ed47db86a2fd4497",
    "homepage": "https://github.com/sindresorhus/del#readme",
    "keywords": [
        "delete",
        "del",
        "remove",
        "destroy",
        "trash",
        "unlink",
        "clean",
        "cleaning",
        "cleanup",
        "rm",
        "rmrf",
        "rimraf",
        "rmdir",
        "glob",
        "gulpfriendly",
        "file",
        "files",
        "folder",
        "dir",
        "directory",
        "fs",
        "filesystem"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "sindresorhus",
            "email": "sindresorhus@gmail.com"
        }
    ],
    "name": "del",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/sindresorhus/del.git"
    },
    "scripts": {
        "test": "xo && ava"
    },
    "version": "2.2.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module del](#apidoc.module.del)
1.  [function <span class="apidocSignatureSpan">del.</span>sync (patterns, opts)](#apidoc.element.del.sync)



# <a name="apidoc.module.del"></a>[module del](#apidoc.module.del)

#### <a name="apidoc.element.del.sync"></a>[function <span class="apidocSignatureSpan">del.</span>sync (patterns, opts)](#apidoc.element.del.sync)
- description and source-code
```javascript
sync = function (patterns, opts) {
	opts = objectAssign({}, opts);

	var force = opts.force;
	delete opts.force;

	var dryRun = opts.dryRun;
	delete opts.dryRun;

	return globby.sync(patterns, opts).map(function (file) {
		if (!force) {
			safeCheck(file);
		}

		file = path.resolve(opts.cwd || '', file);

		if (!dryRun) {
			rimraf.sync(file);
		}

		return file;
	});
}
```
- example usage
```shell
...

	var force = opts.force;
	delete opts.force;

	var dryRun = opts.dryRun;
	delete opts.dryRun;

	return globby.sync(patterns, opts).map(function (file) {
		if (!force) {
			safeCheck(file);
		}

		file = path.resolve(opts.cwd || '', file);

		if (!dryRun) {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
