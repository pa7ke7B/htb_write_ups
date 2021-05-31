# README

Laboratory is an easy Linux box from HTB that involves exploits around Gitlab.

## Network Configuration

IP Address: 10.10.10.216

## Issues

- Unable to establish a reverse shell to https://git.laboratory.htb. 

Steps to recreate issue:
1. Start up the docker instance of gitlab
2. Once inside gitlab bash, run command to open up gitlab-rails shell
3. Run Deserialize Payload to get access token to https://git.laboratory.htb/users/sign_in
4. Run netcat command to listen on port emphasized in the payload
5. Run curl command: ```curl -vvv -k 'https://git.laboratory.htb/users/sign_in' -b "experimentation_subject_id=ACCESS_TOKEN"```
7. ERROR: Reverse shell does not start up from shell running the netcat cmd





