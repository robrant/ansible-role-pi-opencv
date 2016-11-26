
Install Open CV with Python Bindings on a Raspberry Pi.

# About

Ansible role for installing opencv on a raspberry pi with Python bindings.

# Usage

Drop into your own playbook using something similar to:

    - hosts: pis
      roles:
        - opencv-python
      tags: opencv

# Credit

The role is based on the great manual instructions provided on this [pyelasticsearch blog post](http://www.pyimagesearch.com/2015/10/26/how-to-install-opencv-3-on-raspbian-jessie/).

# Works On

Tested on Raspbian Jessie.
