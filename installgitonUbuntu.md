# Install and configure Git on Ubuntu

## Commands to install Git
```
sudo apt update

sudo apt install git
```

### To view the Git version after installation:
```
git --version
```

### Integrate GitHub account with Git

```
git config --global user.name "xyz"
git config --global user.email "xyz@gm.com"

```
### To view the global config variables

```
git config --list
```

### git clone

### git status

### git add filename

### git commit -m "message"

![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/9bf2d910-6f21-4a7f-b201-a50eb690a206)


### git push origin main
It will ask for GitHub username and password.
Password authentication will not work.

![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/3a6258b1-6c91-4d27-9394-3912b2901279)


### Configure authentication method

- Go to GitHub-> Settings -> Developer Settings -> Personal access tokens (classic) -> Generate new token (classic)
  
  ![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/2a797817-9252-4962-be00-d3fa4212647b)

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

![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/4068d6c3-0b37-45f1-8417-12e9adcca70d)


### Viewing branches
```
git branch -a
```
Asterik denotes the current branch.

### Creating new branch

```
git checkout -b develop
```
![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/366bef47-f23b-4fa4-ac8d-8692ec0bd154)

### Switching branches
```
git checkout main
```
![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/04038756-09ad-4591-9298-a092df83ea1f)








