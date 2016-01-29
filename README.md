# test-nxos
Playbooks for testing Ansible modules with Cisco NXOS devices

```
$ ansible-playbook all.yaml
```

Test cases are added to roles based on the module it is testing.  Test cases
should include both `cli` and `nxapi` test cases.  Cli test cases should be
added to role/tests/cli and nxapi tests should be added to
role/tests/nxapi.

To filter a singular test cases, pass the testcase argument on the command line

```
$ ansible-playbook all.yaml -e "testcase=sublevel"
```

