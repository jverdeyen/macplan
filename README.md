# Easy Mac OS X setup with Ansible



## Step 1: Install Xcode
Grab a cup of coffee, this will take while.

```
xcode-select --install
```

## Step 2: Install Homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Step 3: Install Ansible and Git
```
export PATH=/usr/local/bin:$PATH
brew install ansible git
```

## Step 4: Clone mac-setup repository
```
git clone [url-of-this-or-your-repo]
cd mac-setup
```

## Step 5: vars.yml
Duplicate `vars.yml.dist` to `vars.yml` and adjust to your needs.
```
cp vars.yml.dist vars.yml
```

## Step 6: Run Ansible playbook
```
ansible-playbook setup.yml --ask-sudo-pass
```

Or run specific tagged roles:
```
ansible-playbook setup.yml --tags osx --ask-sudo-pass
```

## Step 7: Run mackup restore

**Wait until Dropbox is done with syncing**

```
mackup restore
```

# Inspired by
* [osx-for-hackers.sh](https://gist.github.com/brandonb927/3195465)
* [ideasonpurpose/ansible-playbooks](https://github.com/ideasonpurpose/ansible-playbooks)
* [mackup](https://github.com/lra/mackup)