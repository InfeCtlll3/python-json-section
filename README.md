# python-json-section

Python-json-section is a script to bring "section" features to the unix shell. Instead of querying using jq or similar tools, this script simulates Ciscos IOS "section" command.

This script only works for JSON at the moment and it brings the JSON section or nest based on its opening and closing brackets.

## Installation

Use the package manager pip to install the package:

```bash
pip install json-section
```

or from source:

```bash
git clone https://github.com/InfeCtlll3/python-json-section.git
cd python-json-section
pip install -e .
```
## Adding folder to the Path
On linux systems, there is a chance that the directory ~/.local/bin is not included by default in your PATH. This directory is used for pip to create links for scripts and binaries. 

In case it is not configured, you should receive the following message upon installing:
```bash
The script section is installed in '/home/<user>/.local/bin' which is not on PATH.
```

That said, in order to invoke the ```section``` command from your shell, you will need to add this directory to your PATH.

On zsh:
```bash
path+=('/home/$USER/.local/bin')
```

On bash, please check [This Link](https://stackoverflow.com/questions/14637979/how-to-permanently-set-path-on-linux-unix) 


## Usage

sample.json
```json
{
  "key" : {
    "anotherKey" : {
      "yetanotherKey": "value"
    }
  }
}
```

command:
```bash
cat sample.json | section value
```

output:
```bash
    "anotherKey" : {

      "yetanotherKey": "value"

    }
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Issues
Please open a issue or mail me at contato.carmando@gmail.com

## Features to come
Support for YAML

## License
[MIT](https://choosealicense.com/licenses/mit/)
