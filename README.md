# GitHub-Verified-Commit

1. To make github verified first generate a rsa certificate

    gpg --full-generate-key

2. Select RSA and RSA default

3. It should be '4096' bit long

4. Select '0' as never expired

5. confirm 'y' 

6. Take exit as O

7. If you want to secure the certificate provide password or else leave blank

8. When ask if not entered password, leave blank and press ok

9. List you newly generate key 

    gpg --full-generate-key

10. Export it 

    gpg --armor --export [key]

11. you key should be after rsa4096/[key]

12. It will give you a certificate, copy it to your github setting under GPG Key

13. Make change to you commit setting by 

    git config --global commit.gpgsign true

14. If faced issue while commiting go to c://users//[user]/.gitconfig and add line under [user]
    signingKey=[key]

TIPS:

if gpg is down run below command -

 gpg-connect-agent -v
