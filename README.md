vector-role
=========

Устанавливает и настраивает Vector.

Requirements
------------

Debian/Ubuntu (APT).

Role Variables
--------------

- `vector_version` (string) — версия Vector, напр. `0.34.1`
- `vector_config_path` — путь конфига, по умолчанию `/etc/vector/vector.yaml`
- `vector_sources` — словарь sources
- `vector_sinks` — словарь sinks


Example Playbook
----------------

```yaml
- hosts: vector
  become: true
  roles:
    - role: vector
      vector_version: "0.34.1"
      vector_config_path: /etc/vector/vector.yaml
      
      vector_sources:
        demo_logs:
          type: demo_logs
          format: syslog

      vector_sinks:
        out:
          type: console
          inputs: ["demo_logs"]
          encoding:
            codec: json
```

License
-------

BSD

Author Information
------------------

Andrey Chernyshov  
System Administrator  
GitHub: https://github.com/ANDREYTOLOGY
# mnt-homeworks-testing
