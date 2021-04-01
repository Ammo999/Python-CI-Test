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


