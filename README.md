Ansible Role Setup Sealedsecret
=========

Role to create a sealed secret deployment on a kubernetes cluster



Role Variables
--------------

```
    SEALED_SECRET_RELEASE: Release version to install, [More info](https://github.com/bitnami-labs/sealed-secrets/releases)
    SEALED_SECRET_KEY: Key pair to decrypt secrets
    SEALED_SECRET_CERTIFICATE: Key pair to decrypt secrets
```

Example Playbook
----------------


```
- hosts: "{{ lookup('env','BASTION_IP') }}"
  become: no
  remote_user: "ubuntu"
    - role: sealed-secret
      SEALED_SECRET_KEY: "{{ lookup('env', 'SEALED_SECRET_KEY') }}"
      SEALED_SECRET_CERTIFICATE: "{{ lookup('env', 'SEALED_SECRET_CERTIFICATE') }}"
      SEALED_SECRET_RELEASE: "{{ lookup('env', 'SEALED_SECRET_RELEASE') }}"
```


Author Information
------------------

- [César vergara](mailto:cvergarae@smu.cl)