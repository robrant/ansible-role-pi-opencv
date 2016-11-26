
# About

Ansible role for installing opencv on a raspberry pi with Python bindings.

# Usage

Drop into your own playbook using something similar to:

  - hosts: pis
    roles:
      - opencv-python
    tags: opencv
