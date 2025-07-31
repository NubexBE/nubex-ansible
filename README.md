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
├── ansible.cfg
├── requirements.yml
└── README.md
```


## Usage

1. **Run ansible-pull**:
   ```sh
   ansible-pull -U https://github.com/your-org/nubex-ansible.git -i inventory/localhost playbooks/bootstrap.yml
   ```

   - `-U`: URL of this repository
   - `-i`: Path to the inventory file
   - The last argument is the main playbook to execute

## References

- [Ansible Pull Documentation](https://docs.ansible.com/ansible/latest/cli/ansible-pull.html)
- [Ansible Best Practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)