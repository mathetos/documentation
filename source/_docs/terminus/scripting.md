---
title: Terminus Manual
subtitle: Scripting Terminus
description: Automate your workflow with Terminus.
terminuspage: true
type: terminuspage
layout: terminuspage
nexturl: terminus/plugins/
previousurl: terminus/commands/
permalink: docs/terminus/:basename/
image: terminus-thumbLarge
searchboost: 100
---

While Terminus makes it easy to manually manipulate the Pantheon environment from your command line, its real value is in scripting. By adding Terminus to your automated tasks, you can truly make Pantheon a part of your standardized workflow.

Consider the repetitive tasks you perform using the Pantheon Dashboard:

 - Can those tasks be executed by Terminus commands?
 - Can the values required by the commands be derived programmatically?

If so, you consider how you can turn the task into a script.

## Authentication

To streamline your use of Terminus in scripts, make sure that it's authenticated first. The recommended method is to use a [machine token](/docs/terminus/install#machine-token).

## Examples

 - The [Pantheon Example Terminus Auto Update Script](https://github.com/pantheon-systems/example-terminus-auto-update-script){.external} demonstrates how you can use Terminus to automate plugin and theme updating for multiple sites.


 - The [Example WordPress Composer](https://github.com/pantheon-systems/example-wordpress-composer){.external} uses Terminus to [deploy staged changes](https://github.com/pantheon-systems/example-wordpress-composer/blob/master/.circleci/deploy}to-pantheon.sh){.external} to multidev environments.


## Bash Variables

One of the ways Terminus can be used in script is the generation of environment variables. In the example below, we use the output of `terminus multidev:list` to create an environment variable with all our multidev environments:

```bash
PANTHEON_MULTIDEV_LIST="$(terminus multidev:list -n ${TERMINUS_SITE} --format=list --field=Name)"
```

This example assumes the variable `TERMINUS_SITE` is already set.
