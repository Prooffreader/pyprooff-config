# Docs summary

### USAGE

    pylint path/to/dir
    pylint path/to/file.py
    pylint path/to/file1.py path/to/file2.py path/to/another/dir  # etc

### CODES AND NAMES

Each pylint message has a code and a longer name, e.g. `C0301`, `line-too-long`. The codes and names are interchangeable.

The first letter of each code refers to the following:

    C: Convention (e.g. line length)
    I: Information
    E: Error (something which will cause the linted file to fail)
    F: Fatal (something which will cause pylint itself to exit early)
    R: Refactor (e.g. too many branches in an if-elif-else block)
    W: Warning (e.g. inconsistent indentation)
    RP: Used to control Pylint's reports

### CONFIGURATION FILE LOCATION:

Pylint's configuration file is called pylintrc; note that sometimes it takes a leading dot (.pylintrc), sometimes it does not. You can generate a config file based on your current settings (a default config file if you have no valid current pylintrc) with pylint --generate-rcfile. Pylint will look for config files in this order (note that if a config file is found, pylint will stop looking; i.e. it's not like cascading style sheets, it won't combine different files)

    1. pylintrc in current working directory
    2. .pylintrc in current working directory
    3. The first pylintrc file it finds upstream of current working directory if current directory is in a package of modules with __init__.py files
    4. A file (with any name) specified by the environment variable pylintrc
    5. ~/.pylintrc as long as your home directory is not /root
    6. ~/.config/pylintrc as long as your home directory is not /root
    7. /etc/pylintrc (a global last-resort config file for all users)

All of these can be overridden at the command line by running `pylint --rcfile=path/to/file`

### TURNING OFF ERROR MESSAGES

Let's say you have a bad indentation error (`W0311`, `bad-indentation`) and you want to silence it. There are two ways:

1. To silence it for one line, put `# pylint: disable=W0311` at the end of that line. It will apply to that line only.
2. To silence it for a block of code from that line onwards, put `# pylint: disable=W0311` alone on a line before the block to be silenced. To re-enable it later, you put `# pylint: enable=W0311` alone on a line.

Note you can always use the error name, e.g. `bad-indentation`, instead of the code.
