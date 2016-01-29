# test-nxos
Playbooks for testing Ansible modules with Cisco NXOS devices

```
$ ansible-playbook all.yaml
```

To filter a singular test cases, pass the testcase argument on the command line

```
$ ansible-playbook all.yaml -e "testcase=sublevel"
```

## Contributing Test Cases 

Test cases are added to roles based on the module being testing. Test cases
should include both `cli` and `nxapi` test cases. Cli test cases should be
added to role/tests/cli and nxapi tests should be added to
role/tests/nxapi.

### Conventions

- Each test case should generally follow the pattern:

  >setup —> test —> assert —> test again (idempotent) —> assert —> done

  This keeps test playbooks from becoming monolithic and difficult to
  troubleshoot.

- Include a name for each task that is not an assertion. (It's OK to add names
  to assertsion too, but the idea is to make it as easy as possilbe when 
  troubleshooting broken tests.)

## License

Provided under the [GPLv3](https://github.com/ansible-testing/test-nxos/blob/master/LICENSE) license. 

## Authors

Created and sponsored by [RedHat | Ansible](http://ansible.com).

