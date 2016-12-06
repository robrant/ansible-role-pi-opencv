
Install Open CV with Python Bindings on a Raspberry Pi.

# About

Ansible role for installing opencv on a raspberry pi with Python bindings.

# Dependencies

* Patience and a little time.
* An internet connection.
* For info - this play downloads and installs a lot of additional libraries from the apt repo. The list is broken into 4 tasks in `./tasks/main.yml`

# Usage

Drop into your own playbook using something similar to:

    - hosts: pis
      roles:
        - opencv-python
      tags: opencv

## Tags

The playbook includes some tags to allow you to run specific groups of tasks more easily. You won't need them obviously, but they can be useful for debugging or following along if you want to. Once you've dropped this role into your playbook, you'll be able to run commands like:

    # Run the whole installation
    $> ansible-playbook -i hosts playbook.yml --tags=opencv

    # Just install the linux dependencies.
    $> ansible-playbook -i hosts playbook.yml --tags=opencv_dependencies

    # Install the python development headers.
    $> ansible-playbook -i hosts playbook.yml --tags=opencv_python_dev

    # Download and install opencv and opencv-contrib.
    $> ansible-playbook -i hosts playbook.yml --tags=opencv_download_unzip

    # Install pip and numpy.
    $> ansible-playbook -i hosts playbook.yml --tags=opencv_python_dependencies

    # Make and make install opencv.
    $> ansible-playbook -i hosts playbook.yml --tags=opencv_make_and_install

    # Test we can access opencv in python.
    $> ansible-playbook -i hosts playbook.yml --tags=test_opencv_install

Tags can be found in `./tasks/main.yml`.

# Credit

The role is based on the great manual instructions provided on the [pyelasticsearch blog](http://www.pyimagesearch.com/2015/10/26/how-to-install-opencv-3-on-raspbian-jessie/).

# Works On

Tested on Raspbian Jessie (November 2016) and Raspbian Jessie minimal image running on a Raspberry Pi B+. It assumes you've done stuff like:

  * Expanded the filesystem.
  * Enabled the Pi to handle SSH (as of November 2016, no longer the default).
