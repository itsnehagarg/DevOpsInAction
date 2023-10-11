# Install Git on Ubuntu

## Commands to install Git
```
sudo apt update

sudo apt install git
```

### To view the Git version after installation:
```
git --version
```
![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/a320e387-badb-41bb-b916-c43df7cd2de4)

### Integrate GitHub account with Git

```
git config --global user.name "xyz"
git config --global user.name "xyz@gm.com"

```
### To view the global config variables

```
git config --list
```

### git clone

### git status

### git add filename

### git commit -m "message"

### git push origin main
It will ask for gitHub username and password.
Password authentication will not work.

### Configure authentication method

- Go to GitHub-> Settings -> Developer Settings -> Personal access tokens (classic) -> Generate new token (classic)
- give the note
- give the expiration date
- Select scope-> select the required options
- click on generate token
- copy the token and save it.
- Use the below command:

```
 git remote set-url origin https://<token>@github.com/<username>/<repo>

```

### Again give the command git push origin main for pushing the code to the repository.








