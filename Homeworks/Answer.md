## Answer by Group 5

## Homework 1

    `dpkg -l`                                     `rpm -qa`
    `dpkg -l {package_name}`                      `rpm -qa {package_name}`
    `dpkg -L {package_name}`                      `rpm -ql {package_name}`
    `dpkg -i {package_name}`                      `rpm -ihv {package_name}`
    `dpkg -r {package_name}`                      `rpm -e {package_name}`
    `dpkg -P {package_name}`                      `rpm -e {package_name}`
    `dpkg -c {package_name}`                      `rpm -qlvp {package_name}`
    `dpkg -S {/path/to/file}`                     `rpm -qf {/path/to/file}`
    `dpkg -p {package_name}`                      `rpm -q {package_name}`
    `dpkg -s {package_name}`                      `rpm -qi {package_name}`
    `dpkg --get-selections`                       Not found

    `apt policy`                                  Not found
    `add-apt repository {repository_name}`        `yum-config-manager --add-repo {repo_url}`
    `apt list`                                    `yum repolist`
    `apt install {package_name}`                  `yum install {package_name}`
    `apt search {package_name}`                   `yum search {package_name}`
    `apt update`                                  `yum check-update`
    `apt upgrade`                                 `yum upgrade`
    `apt remove {package_name}`                   `yum erase {package_name}`
    `apt purge {package_name}`                    `yum remove {package_name}`
    `apt autoremove`                              `yum autoremove`

## Homework 2
    $ sudo apt install alien
    $ alien bless-0.6.0-21.fc26.aarch64.rpm
    $ sudo dpkg -i bless-0.6.0-21.fc26.aarch64.deb

## Homework 3
    ```
    function last_modified() {
        find . -type f -printf '%AD+%Ar %p\n' | sort -k1,1nr | head -5
    }

    alias l5f_lm=last_modified
    ```

## Homework 4
    ```
    function get_codename() {
        cat /etc/lsb-release | sed -n 3p | awk -F "=" '{print $2}'
    }

    alias gc=get_codename
    ```

## Homework 5
    ```
    function kill_all_process() {
        kill $(ps aux | grep $1 | awk '{print $2}')
    }

    alias kill_all=kill_all_process
    ```

## Homework 6
    ```
    function git_pull_current_branch() {
        git pull origin $(git branch | grep '*' | awk -F " " '{print $2}')
    }

    alias gplo=git_pull_current_branch
    ```
