<!---  
    A rule set for Wazuh to detect live-off-the-land techniques on Linux and Unix systems.
    Copyright (C) 2023 Steffen Fritz <steffen@fritz.wtf>

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU Affero General Public License as published
    by the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU Affero General Public License for more details.

    You should have received a copy of the GNU Affero General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
--->
# wazuh-gtfobins
A rule set for Wazuh to detect live-off-the-land techniques on Linux and Unix systems.

## What are GTFOBins?
From the project's webpage:

"GTFOBins is a curated list of Unix binaries that can be used to bypass local security restrictions in misconfigured systems."

Source: [GTFOBins](https://gtfobins.github.io/)

The thing is that these binaries are not malicious or vulnerable. They can be used in malicious ways. 

This project aims to write process detection rules for [Wazuh](https://wazuh.com/) to detect such usages. 

While there are similar projects like GTFOBins for [Windows](https://lolbas-project.github.io/) and [drivers](https://www.loldrivers.io/), wazuh-gtfobins just implements rules for Linux and Unix.

## How is this project structured?

It follows a simple structure. 

Configurations that have to be made on the Wazuh server are in the subfolder _server_, configurations for the agents are in the subfolder _agent_.

Global configuration files, e.g. ossec.conf, have the suffix _.gtfo_ to prevent accidental overwritings. These snippets have to be added to existing files.

The rule files are in the subfolder _rules_ and are prefixed with a four digit number and a dash, starting with _2000-_. There must be a gap of 10, e.g. _2000-onerule.xml_, _2010-anotherrule.xml_.

## How to contribute?

1. Clone this project
2. Check which rules are not implemented yet in the issues tab (incomplete) or in the rules directory or contact me if unsure
3. Check the example command string from the GTFOBins project
4. Write the rule. Please have a look at existing rules!
5. add - commit - pull request
6. :)
