Oracle Install Role
=========

This role will allow users to copy oracle rpm package form s3 bucket and install oracle.  Currently the only supported OS platform is RedHat. 

Requirements
------------

Must have an oracle rpm package on s3 bucket.
RedHat machine with subscription(enabled).

Role Variables
--------------

oracle_working_directory, oracle_rpm_package, oracle_rpm_package_path, oracle_rpm_bucket_name, oracle_preinstallation_rpm_package_url, oracle_preinstallation_rpm_package_path, compat_libstdc_package_url,
compat_libcap1_package_url.

Dependencies
------------

Role to be attached to EC2 instance to copy oracle rpm package form s3 bucket.
compat-libstdc++-33-3.2.3-72.el7.x86_64.rpm.
compat-libcap1-1.10-7.el7.x86_64.rpm.
oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

---
- hosts: local
  roles:
    - role: install_oracle

  
  vars:  
        oracle_working_directory: "/opt/oracle"
        oracle_preinstallation_rpm_package_url: "https://yum.oracle.com/repo/OracleLinux/OL7/latest/x86_64/getPackage/oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm"
        oracle_preinstallation_rpm_package: "oracle-database-preinstall-19c-1.0-1.el7.x86_64.rpm"
        oracle_preinstallation_rpm_package_path: "{{ oracle_working_directory }}/{{ oracle_preinstallation_rpm_package }}"

        oracle_rpm_package: "oracle-database-ee-19c-1.0-1.x86_64.rpm"
        oracle_rpm_package_path: "{{ oracle_working_directory }}/{{ oracle_rpm_package }}"
        oracle_rpm_bucket_name: "emory-oracle-package"


        compat_libstdc_package_url:  "http://mirror.centos.org/centos/7/os/x86_64/Packages/compat-libstdc++-33-3.2.3-72.el7.x86_64.rpm"
        compat_libstdc_package: "compat-libstdc++-33-3.2.3-72.el7.x86_64.rpm"
        compat_libstdc_package_path: "{{ oracle_working_directory }}/{{ compat_libstdc_package }}"

        compat_libcap1_package_url:  "http://mirror.centos.org/centos/7/os/x86_64/Packages/compat-libcap1-1.10-7.el7.x86_64.rpm"
        compat_libcap1_package: "compat-libcap1-1.10-7.el7.x86_64.rpm"
        compat_libcap1_package_path: "{{ oracle_working_directory }}/{{ compat_libcap1_package }}"

        list_of_packages:
           - "{{ compat_libstdc_package_path }}"
           - "{{ compat_libcap1_package_path }}"
           - "{{ oracle_preinstallation_rpm_package_path }}"



Tower execution examples
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


License
-------

BSD

Author Information
------------------

Created by: Vijay 


