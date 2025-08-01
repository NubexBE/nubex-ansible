# nubex-ansible

This repository contains Ansible playbooks, roles, and configuration for managing infrastructure using `ansible-pull`.

## Repository Structure

```
nubex-ansible/
├── inventory/
│   └── localhost
├── playbooks/
│   └── bootstrap.yml
├── roles/
│   └── geerlingguy.docker/ 
|   └── add_user/ 
├── ansible.cfg
├── requirements.yml
└── README.md
```


## Usage

1. **Install packages**:
    ```sh
    apt update && apt install git ansible -y
    ```

2. **Run ansible-pull**:
   ```sh
   ansible-pull -U https://github.com/NubexBE/nubex-ansible.git -i inventory/localhost playbooks/bootstrap.yml
   ```

   - `-U`: URL of this repository
   - `-i`: Path to the inventory file
   - The last argument is the main playbook to execute

3. **Update add_user Role**:
    
    Add users in bootstrap.yml

   ```yaml
    - role: add_user
      vars:
        users:
          - name: joe           # Example user
            gh_user_name: joe   # Example GitHub username
            groups:             # or ['sudo', 'docker', 'ubuntu']
              - sudo
              - docker
              - ubuntu
          - name: nick
            gh_user_name: nick
            groups: ["sudo"] 
   ```

   or change variable file in Role: /roles/add_user/vars/mian.yaml

   ```yaml
    users:
    - name: joe           # Example user
        gh_user_name: joe   # Example GitHub username
        groups:             # or ['sudo', 'docker', 'ubuntu']
        - sudo
        - docker
        - ubuntu
   ```

## References

- [Ansible Pull Documentation](https://docs.ansible.com/ansible/latest/cli/ansible-pull.html)
- [Ansible Best Practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)