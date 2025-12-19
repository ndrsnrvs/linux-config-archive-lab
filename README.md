# linux-config-archive-lab
RHEL lab demonstrating foundational Linux system administration skills including configuration inspection, text processing, and secure archival of system files.

## Lab Instructions
---
1. Find the all occurences of the string "Listen" in `etc/httpd/conf/httpd.conf/` and save the output to `root/web.txt`.
2. Create a gzip-compressed tar archive of `etc/` named `etc_vault.tar.gz` in `vaults/` directory.
3. Imposed Challenge: Complete the above without using GNOME desktop environment.

### Process:
- At the user login page I used `Ctrl + Alt + F2` to open a new terminal window.
- Once I logged in I navigated to `etc/`, only to discover that the package group I installed with RHEL didn't come with the `httpd/` folder.  After some learning about [Red Hat's Package Manager](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/8/html/packaging_and_distributing_software/introduction-to-rpm_packaging-and-distributing-software) and the commands `dnf`, `yum`, and the difference between installing packages individually vs. in groups I installed the correct package using `dnf install httpd`.
- When in the `etc/httpd/conf/` directory, I grep searched for all occurences of the string "Listen" and redirected the stdout of the `grep "Listen"` to a new file `web.txt` leveraging the standard output redirection operator `>` in `grep "Listen" > web.txt`.
- Next I needed to move this text file to the `root/` folder, to accomplish this I used `mv web.txt root/`.

_I will note that I later discovered that I could've searched for the string I needed to look for and create the `web.txt` file in the correct directory in a single command._
