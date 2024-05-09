

---

# Ansible Playbook for Application Deployment

This Ansible playbook is designed to automate the deployment of a web application on a set of servers using HAProxy as a load balancer.

## Purpose

The purpose of this playbook is to:

1. Update package repositories and cache using `apt update`.
2. Configure HAProxy as a load balancer.
3. Install necessary software packages like HAProxy, Python3, Flask, and Gunicorn.
4. Set up a Flask application on web servers behind the load balancer.
5. Ensure the Flask application is running and accessible.

## Playbook Structure

The playbook is structured as follows:

1. **Update Package Repositories**: The playbook starts with updating the package repositories and cache to ensure the system is up to date.

2. **Configure HAProxy Load Balancer**:
    - Installs HAProxy on the designated HAProxy server.
    - Gathers IP addresses of the web servers.
    - Copies the HAProxy configuration file `haproxy.cfg.j2` to the HAProxy server, ensuring it's configured correctly.
    - Restarts the HAProxy service to apply changes.

3. **Deploy Web Application on Web Servers**:
    - Installs required packages like Python3-pip, Flask, and Gunicorn on the web servers.
    - Creates a directory `/home/flask-app/` for the Flask application.
    - Copies the Flask application file `application2.py` to the web servers.
    - Starts the Flask application using Gunicorn on port 80.

## Usage

To use this playbook:

1. Ensure Ansible is installed on your system.
2. Update the `hosts` file with the IP addresses or hostnames of your servers.
3. Ensure SSH access to the servers is configured correctly (using `ssh_config` or `~/.ssh/config`).
4. Ensure your private key (`id_rsa.txt`) is available and accessible.
5. Run the playbook using the following command:

```bash
ansible-playbook -i hosts playbook.yml
```

## References

- [Ansible Documentation](https://docs.ansible.com/ansible/latest/index.html): Official documentation for Ansible, including installation instructions and usage guides.
- [HAProxy Documentation](https://www.haproxy.com/documentation/): Documentation for HAProxy, including configuration options and best practices.
- [Flask Documentation](https://flask.palletsprojects.com/en/2.0.x/): Flask documentation for building web applications in Python.
- [Gunicorn Documentation](https://docs.gunicorn.org/en/stable/): Documentation for Gunicorn, a Python WSGI HTTP Server for UNIX.

## Notes

- The playbook assumes that your servers are configured to allow SSH access using the specified private key.
- Ensure that the `haproxy.cfg.j2` and `application2.py` files are present in the same directory as the playbook.
- This playbook should be run from a system where Ansible is installed and configured.