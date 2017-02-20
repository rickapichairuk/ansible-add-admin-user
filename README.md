ansible-add-admin-user
========

Adds user account with sudo rights for all commands without password. This
account is usually the one used by the systems administrator or devops engineer
to login to a machine.

Requirements
------------

None.

Role Variables
--------------

* username
  * string
  * a user account will be created with this username
* remove_all_other_sudo_rights
  * boolean (defaults to true)
* use\_key\_from_url
  * boolean (defaults to false)
  * if true, then supply url with following var:
* key_url
  * string
  * url of the public key (https://github.com/user.keys)
* use\_key\_from_file
  * boolean (defaults to false)
  * if true, then supply path with following var
* key_file
  * string
  * path to the key file (/home/user/.ssh/id_rsa.pub)

Example Playbook
-------------------------

```yaml
- hosts: webservers
  roles:
    - role: ansible-add-admin-user
      username: snoopdogg
      # keep all other sudo lines in sudoers file
      remove_all_other_sudo_rights: false
      use_key_url: true
      key_url: https://github.com/snoopdogg.keys
```

Author
------

Rick Apichairuk

License
-------

BSD 3-Clause License

Copyright (c) 2017, Rick Apichairuk
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its
  contributors may be used to endorse or promote products derived from
  this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
