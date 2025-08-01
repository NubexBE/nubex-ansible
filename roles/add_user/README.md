# add_user Role

This Ansible role manages the creation and configuration of user accounts on target systems.

## Requirements

- Ansible 2.9+
- Supported OS: Linux distributions

## Role Variables

| Variable       | Description                | Default           |
|----------------|---------------------------|--------------------|
| `name`         | Name of the user to add   | (required)         |
| `gh_user_name` | User's gh key name        | `joe`        |
| `groups`       | List of groups to add user| `["sudo","admin"]` |

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: add_user
      vars:
        name: "joe"
        gh_user_name: "joe123"
        groups: 
          - sudo
          - developers
```

## License

MIT

## Author Information

NubeX DevOps Team