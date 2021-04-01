# Python-CI-Test
First test to create a Python CI flow

#Hook up Github and Cloud 9
1. Create a git repository, add description
2. Goto AWS Cloud 9
3. AWS: Create a Environment name and description
4. GitHub: Goto user settings, SSH and GPG Keys
5. Github: Create a SSH Title (dont do anything else yet)
6. AWS-C9 (Amazon Cloud 9): goto  bash terminal - type "ssh-keygen -t rsa", press return three times
7. AWS-C9: Copy the XXX from  "Your public key has been saved in XXXXX"
8. AWS-C9: Type "cat " XXXX - this prints the public key
9. AWS-C9: Copy the public key
10. Github: Paste the key into the add-ssh. Enter github password
11. 

#Now create environment in AWS
Github: goto the new repository, copy the git reop code (green code button) ZZZZ. Make sure to use the SSH clone path
AWS-C9: "git clone" ZZZZ, enter "yes" when prompted

# Now create Vitrutal Environment in AWS
AWS-C9: "python3 -m venv ~/.github-python-ci"          (github-python-ci is the name of whaever you choose)
AWS-C9: "source ~/.github-python-ci/bin/activate"      (github-python-ci is the name chosen earlier)
AWS-C9: make a reqirements.txt file to contain all of the packages required
        black
        pylint
        pytest
        pytest-cov
        click
        
AWS-C9: Make Makefile

install:
	    pip install --upgrade pip &&\
		pip install -r requirements.txt

test:
	pytest -vv --cov-report term-missing --cov=app test_*.py

format:
	black *.py

lint:
	pylint --disable=R,C app.py web.py

all: install lint test




