# Build Script for Use with Nextcloud

**This script and repo is unaffiliated with Nextcloud GmbH**

This is a build script for use with Nextcloud.

This script does not include signing or actually releasing a build.

### How to Run

**Requires Node v12 or later**

```bash
npm ci
npm start -- --help
npm start -- build

# Build v17.0.4
npm start -- build --nc-version v17.0.4
```

You can find a list of currently supported Nextcloud build versions in the [configs](configs) directory.

You can also specify a custom config. Look in the help options for that.

### Currently Missing

List of things in the Nextcloud GmbH release that are not in releases made by this script.

* Documentation
    * The Nextcloud GmbH release contains documentation from <https://github.com/nextcloud/documentation>.
    * Planned
* Signing
    * Nextcloud GmbH's release script signs all apps and the release itself.
    * Planned (provide your own keys. Obviously not possible to sign things such that it would pass on currently running Nextcloud instances (that'd defeat the whole point of signing))
* Support app
    * The support app is currently only in a private repo so is not publicly available so cannot be included in these releases. Strictly speaking, it could be pulled out of the official release and repackaged as the `appinfo/info.xml` indicates that it is `agpl` licensed and the entirety of Nextcloud including the releases by Nextcloud GmbH are licensed under `AGPL-3.0-or-later` but the point of this script is to be able to generate releases without having to use the Nextcloud GmbH releases.
* Exclude list different
    * The exact exclude list used is different so some files that are in the Nextcloud GmbH release are excluded in this release. Things such as extra test files are unnecessary but in the Nextcloud GmbH release are removed in this script.

### To do

* Complete everything possible in [Currently Missing](#currently-missing)
* Document how to create new release configs
* Write contributing documentation

### License

Licensed under [AGPL-3.0-or-later](LICENSE)

Copyright &copy; 2020 Gary Kim &lt;<gary@garykim.dev>&gt;
