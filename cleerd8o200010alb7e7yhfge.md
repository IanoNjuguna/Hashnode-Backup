# Set Up your GitHub Commit Signature

I'll list the doc sources in the correct order because they are clear and concise.  
  
Make sure you've [set up your Git](https://hashnode.com/post/clea9ufru000109mof80xffwl).  
  
Here goes:

1. [Generate a GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)
    
2. [Add the GPG key to your GitHub account](https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-gpg-key-to-your-github-account).
    
3. [Tell Git about your GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key).
    

Follow them in that order and you will not encounter any problems.

To sign your commits, you need to run the `git commit` command like this:

```bash
$ git commit -S -m "Commit Message"
```

However, to customize the command and make it easier to remember or quicker to type, learn how to create a permanent alias.