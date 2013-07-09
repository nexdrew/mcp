"I can deploy things 900 to 1200 times better than any human..."
================================================================

Master Control Program is a configurable Gradle-based script to
execute deployment commands against remote hosts from a central
location.

MCP is the local CLI that tells [Sark](https://github.com/nexdrew/sark)
(a light-weight Gradle-based deployment "agent") what to do.

For a quick example, MCP can remotely deploy your version 1.0.0 artifacts
to multiple configured hosts concurrently via:

    $ ./mcp deploy %1.0.0 @host1 @host2 @host3 --parallel

How does it work?
=================

Magic.

Actually, like most good henchmen, [Sark](https://github.com/nexdrew/sark)
does most of the work. MCP just uses SSH to issue predefined commands against
remote Sark "agents".

Sark knows which applications/artifacts to download, where to download them
from (a Maven repository), where to copy them to, and which services (if any)
to stop and start. Take a look at 

MCP just gives you a central interface to manage your Sark "agents" so
you don't have to open multiple SSH terminal sessions and issue separate
commands yourself.

MCP is really just a couple properties files and a shell script. MCP uses
[Gradle](http://www.gradle.org/) and the [gradle-ssh-plugin](https://github.com/int128/gradle-ssh-plugin) 
under-the-hood.

TBD
===

- How to use
- Installation/setup

Copyright 2013 Andrew Goode
Licensed under the Apache License 2.0
See LICENSE file for details
