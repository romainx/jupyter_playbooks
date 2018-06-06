# Jupyter Playbooks

Installation of **Jupyter + JupyterHub** in different flavors.

## Standalone installation

### Features

Install JupyterHub in JupyterLab mode over a Ubuntu 16.04.4 LTS by using an Anaconda distribution.

Security:

- nginx with SSL
- certificate can be: provided, self-signed or managed by [Let’s Encrypt][LK_1]
- [cookie secret][LK_2]

Authentication / Authorization:

- PAM with local users
- OAuth2

### How to

See the content of the playbook by running

```
$ ansible-playbook -i ./hosts jupyter_standalone.yml --list-tasks
```

The TCP port 443 must be open in order to be able to serve notebooks in HTTPS.

### Known problems

When stopping JupyterHub, the `configurable-http-proxy` remains up. This prevent to restart JupyterHub. 
It's necessary to kill the process to be able to relaunch JupyterHub properly.

### Sources

Inspired by [jupyterhub-deploy-teaching](https://github.com/jupyterhub/jupyterhub-deploy-teaching)

[LK_1]: https://letsencrypt.org/
[LK_2]: http://jupyterhub.readthedocs.io/en/latest/getting-started/security-basics.html#cookie-secret