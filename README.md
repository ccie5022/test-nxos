# test-nxos
Playbooks for testing Ansible modules with Cisco NXOS devices

```
$ ansible-playbook all.yaml
```

To filter a singular test cases, pass the testcase argument on the command line

```
$ ansible-playbook all.yaml -e "testcase=sublevel"
```

## Adding Test Cases 
Test cases are added to roles based on the module it is testing.  Test cases
should include both `cli` and `nxapi` test cases.  Cli test cases should be
added to role/tests/cli and nxapi tests should be added to
role/tests/nxapi.

### Conventions

Each test case should generally follow the pattern:
>setup —> test —> assert —> test again (idempotent) —> assert —> done

This should keep test playbooks from becoming monolithic and difficult to
troubleshoot.

Include a name for each task that is not as assertion. It's OK to add names
to assertsion too, but the idea is to make it as simple as possilbe when 
troubleshooting broken tests. 

