---
- name: Deploy app with vault secrets
  hosts: dev
  become: yes

  tasks:
    - name: Create directory for app
      ansible.builtin.file:
        path: /opt/myapp
        state: directory
        mode: '0755'

    - name: Create .env file with secrets
      ansible.builtin.copy:
        dest: /opt/myapp/.env
        content: |
          APP_PASSWORD={{ app_password }}
          DB_PASSWORD={{ db_password }}
          API_TOKEN={{ api_token }}
        mode: '0644'

    - name: Show app password
      ansible.builtin.debug:
        msg: "App password is {{ app_password }}"
