# Formatless

Formatless provides a data format agnostic adapter for command-line tools like `npm` or `bower`.

# Installation
<!-- `npm install -g formatless` to install the adapter tool. -->
Formatless is still under development.

# Usage
`formatless run [command] <file1> <file2> <file3...>`
`formatless run [command] <options>`
`formatless watch <file1> <file2> <file3...>`
`formatless curry [command] <alias>`

`.formatlessrc`
`~/.formatlessrc_global`

# Examples
`formatless run npm install`
`formatless run "npm install -g formatless"`

`formatless run npm install --using="package.json" --source="package.cson"`
`formatless run npm -c install package.json`
`formatless run npm --command="install -g formatless" package.json`

`formatless run bower install -w bower.json:bower.cson -w .bowerrc:.bowerrc.cson`
`formatless run bower install --with="bower.json:bower.cson" --with=".bowerrc:.bowerrc.cson"`
`formatless run bower install --with="bower.json:bower.cson, .bowerrc:.bowerrc.cson"`
`formatless run bower install --with="bower.json:bower.cson; .bowerrc:.bowerrc.cson"`
`formatless run "bower install -p" bower.json:bower.cson .bowerrc:.bowerrc.cson`

# Configuration
```
{
  "commands": {
    "npm": "package.json",
    "bower": ["bower.json", ".bowerrc"],
    "gulp": [{
      "Gulpfile.coffee": "Gulpfile.js"
    }],
    "broccoli": [{
      "output": {
        "name": "Brocfile",
        "format": "js"
      },
      "source": {
        "name": "Brocfilerc",
        "format": "CoffeeScript"
      }
    }]
  },
  "files": {
    ".bowerrc": {
      "format": "json"
    }
  }
}
```
