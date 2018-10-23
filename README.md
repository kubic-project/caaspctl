# `caaspctl`: a simple, scriptable _cli_ for CaaSP

## Usage

You can enter the cli:

```bash
$ caaspctl
CaaSP control tool.

caaspctl > pillar
caaspctl:pillar > ?

Documented commands (type help <topic>):
========================================
db     get   load   quiet  refresh  shell  traceback
flush  help  print  quit   set      stage

Undocumented commands:
======================
EOF  eval

caaspctl:pillar > ? set

        Set a pillar in the database.

        Usage:

        > pillar set api:server:external_fqdn 192.168.122.4
        
caaspctl:pillar > set api:server:external_fqdn 192.168.122.4
```

or you can run commands directly as arguments

```bash
$ caaspctl pillar set api:server:external_fqdn 192.168.122.4
```

or you can run all your commands in a script

```bash
$ cat <<EOF>myscript.txt
# wait for velum to be ready before going forward
cont wait velum

# accept all the three minions
accept 3

# and then set some pillar
pillar set api:server:external_fqdn 192.168.122.4
EOF

$ caaspctl --script myscript.txt
```

## Status

Alpha, we are still fixing bugs...



