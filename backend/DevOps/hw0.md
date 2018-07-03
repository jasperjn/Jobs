# DevOps Homework0

* Except explicitly specified in the question, you could implement by your own way.
* Answering question is requirement; you are free to show us what you can do. Astonish us!

# 0 - Git

- Please create a repository for answering following questions. You could choose any platform you like, like github, gitlab, bitbucket, etc.
- Please create branch for each question, for example `1-docker`, `2-linux`, and answer on corresponding branch.
- Merge them into `master` branch. we only examine answers on `master` branch.
- Email us your repository link.

# 1 - Docker

## 1.1
Please explain this command.
```
docker run \
	-d \
	-e TEST_ENV=HELLO_WORLD \
	-v /etc/localtime:/etc/localtime:ro \
	-p 8080:80 \
	-p 5566:443 \
	--link mysql:db \
	--dns=10.0.0.1 \
	--dns=192.168.0.1 \
	--dns-search=local.test.com \
	--dns-search=test.com \
	--name test_docker \
	registry.local.test.com/infra/test_docker:0-17.08.03-caf85b05-rc
```

## 1.2
Please explain this command.
```
docker rmi $(docker images | grep "^<none>" | awk "{print $3}")
```

# 2 - Linux
Please explain the functionality of the following two files in Linux operation system.
```
/etc/hosts
/etc/resolv.conf
```

# 3 - Programming
Please write a program to read [access.log](access.log);
find out the logs with `return code 404`;
count the occurrence of each IP among these logs and output them in ascending order.

Expected output:
```
1 118.163.135.13
1 123.51.165.114
1 210.242.60.1
1 210.243.21.253
1 220.134.215.89
1 59.125.23.30
1 60.250.66.98
1 74.222.14.82
3 64.71.171.80
4 64.71.171.86
```

You may use any language you like; please include your code in the repository and teach us how to reproduce your result.


# 4 - Questionnaire
1. How long did you spend answering?
2. Which question is the most easy for you? Why?
3. Which question is the most difficult for you? Why?
4. Regarding your working style, when coding, do you prefer to work alone or in teams? Same question but when you are doing design and/or research. 
5. From what you have surveyed, what aspect of Bridgewell matches you the most? What aspect match you the least?
6. What kind of contribution you expect to make to Bridgewell?
7. What do you expect to take away from Bridgewell?
