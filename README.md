Lighthouse
=========

Учебная Ansible роль для установки [Lighthouse от VK](https://github.com/VKCOM/lighthouse)

Requirements
------------

Ожидает наличия от `git` и `nginx` на сервере

Role Variables
--------------

| Переменная | Тип | Значение по умоланию | Комментарий |
| --- | --- | --- | --- |
| `lighthouse_dir` | Строка | /opt/lighthouse | Папка, в которую загружены скрипты Lighthouse |
| `lighthouse_access_log` | Строка | lighthouse_access | Имя файла в рамках nginx с логами доступа /var/log/nginx/lighthouse_access_log.log |

Dependencies
------------

- См. Requirements

Example Playbook
----------------

```yml
- name: Install Lighthouse
  hosts: lighthouse
  pre_tasks:
    - name: Install Lighthouse | Install git
      become: true
      ansible.builtin.yum:
        name: git
        state: present
  roles:
    - nginx
    - lighthouse
```

License
-------

MIT
