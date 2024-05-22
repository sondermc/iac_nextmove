# Current
As part of the current state I see a lot of scripting steps. 

## classic pipelines
Referring to Azure and Jenkins, I mostly see scripted steps.
For instance when some extra piece of software is required, it seems pretty normal to script this and I run into command/script patterns like this:
* install curl, bzip
* use curl to fetch a tar.gz file
* create a target directory
* changedir to this directory
* extract the downloaded file in this directory
* change ownership
* change file modes

## Yaml pipelines
The same pattern is seen

## Ansible
Even in Ansible, the use of the module 'ansible.builtin.script' or 'ansible.builtin.command' seems the default module of choise. I bump into similar patterns as described under 'classic pipelines'

# Issue
Although this situation will eventually lead to a working state, one needs to ask themselve: "What happens if I run this pipeline for the second time?", or "How do I know from a running system if the correct (approved) software is installed and used?"
