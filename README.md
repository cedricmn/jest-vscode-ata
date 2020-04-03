# Feature request

Visual Studio Code should download @types/jest with this jsconfig.json configuration :

```json
{
    "typeAcquisition": {
        "include": [
            "jest"
        ]
    }
}
```

But Automatic Type Acquisition give priority to Jest types coming from node_modules :

```
[23:20:24.533] Explicitly included types: ["jest"]
[23:20:24.534] Typing names in '/data/www/jest-vscode-ata/package.json' dependencies: ["jest"]
[23:20:24.578] Searching for typing names in /data/www/jest-vscode-ata/node_modules; all files: [...]
[23:20:24.632]     Package 'jest' provides its own types.
```

Provided Jest types seems to be useless and they are not globally available. Automatic Type Acquisition should give the ability to prioritize jsconfig.json configuration over node_modules types.

# Configuration

- VSCode Version: 1.43.2
- OS Version: Debian 10 / Xfce 4.12

# Demo repository

- git clone https://github.com/cedricmn/jest-vscode-ata.git
- Open index.test.js with Visual Studio Code
- Jest autocomplete does not works

# Workaround

- Installing @types/jest as dev dependency fix the issue but typing should be Automatic Type Acquisition responsibility
- Installing Jest globally and removing it from dev dependency fix the issue but Jest should be listed as dev dependency
