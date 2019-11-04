# pylint README

### from Prooffreader/pyprooff-config


This section of the repo is organized as follows:

|- **README-pylint.md** : this file
|- **__version**__ : pylint version this repo is based on (most recent when started)
|- *default/* : default values in various formats for various config concepts
    |- *pylintrc/* : default pylintrc file
    |   |- **pylintrc-default** : default pylintrc produced by #TODO
    |- error_messages/ : various pylint error messages and codes
        |- *01_output_of_pylint_--list_msgs/* : output of command pylint --list_msgs
        |   # note that is is not "complete", i.e. it does not include some codes/messages
        |   # that have been deprecated, but still might appear in some contextx
            |- **01_pylint_msgs-raw_output.txt** : exact copy of stdout from putlint --list_msgs
            |- **02_pylint_msgs_reformatted_for_pylintrc.txt** : previous file reformatted
            |  # so it can be copied and pasted to pylintrc and used as is
            |- **03_pylint_msgs.json** : JSON file of pylint --list_msgs
