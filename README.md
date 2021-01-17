
# Node Cron CLI

Command Line Implementation for Node Cron Under 20 Lines.

## Quick Start

This will execute your specified command `pwd` each 2 seconds.

```
./cron-cli.js -p "*/2 * * * * *" -e "pwd" --log
```

## Installation

```
git clone https://github.com/yuis-ice/node-cron-cli.git && cd node-cron-cli && chmod 755 ./cron-cli.js
npm i
```

## Examples

Every hour
```
0 0 * * * *
```

Every day
```
0 0 0 * * *
```

Every 4 hours
```
0 0 */4 * * *
```

Every day at 11am and 11pm
```
0 0 11,23 * * *
```

For more info, see [kelektiv/node-cron](https://github.com/kelektiv/node-cron)

## Command line options

```
$ ./cron-cli.js
Usage: cron-cli [options]

Options:
  -p, --pattern <pattern>    cron pattern  (default: "*/5 * * * * *")
  -t, --timezone <timezone>  timezone  (default: "Asia/Tokyo")
  -e, --execute <command>    command to be executed  (default: "echo Hi.")
  -l, --log                  enable console log
  -h, --help                 display help for command
```

## LICENSE

This software is released under the BSD-3-Clause license.
