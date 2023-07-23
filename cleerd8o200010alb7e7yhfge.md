---
title: "Set Up your GitHub Commit Signature"
seoTitle: "Set Up GitHub Commit Signature"
seoDescription: "Learn the benefits of setting up a GitHub commit signature. Enhance code integrity, build trust, and secure collaborations. Easy setup guide inside!"
datePublished: Tue Feb 21 2023 21:28:12 GMT+0000 (Coordinated Universal Time)
cuid: cleerd8o200010alb7e7yhfge
slug: set-up-your-github-commit-signature
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1677014730459/f2def28e-6136-4dde-ac77-e724c718571e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690141735713/e4929cc4-e140-446f-9157-134051ac7171.png
tags: commit, github, version-control, beginners, commit-messages

---

## Introduction

Once you set up your commit signature, the commits are signed "verified". Before then, they are signed "unverified".
  <a href="https://github.com/yourRepo">
  <p align="center">
    <img width="600" height="300" src="https://pbs.twimg.com/media/F1viFOJWcAAj5lo?format=png&name=360x360">
  </p>
</a>
Before setting up your commit signature, make sure you've [set up your Git](https://hashnode.com/post/clea9ufru000109mof80xffwl).

## Why Should You Set Up Your Commit Signature?

1. **Data Integrity and Authenticity**: Commit signatures use cryptographic techniques to ensure the integrity and authenticity of your code changes. This means that others can be confident that the code attributed to you is legitimate and has not been altered by unauthorized parties.

2. **Build Trust and Reputation**: Commit signatures enhance your credibility as a developer, especially when contributing to open-source projects or collaborating with others. Trust is crucial in the software development community, and signed commits can help build a positive reputation.

3. **Secure Collaboration**: With signed commits, team members can easily verify the origin of changes, reducing the risk of accepting malicious or unauthorized code into the project. It fosters a more secure collaboration environment.

4. **Compliance and Legal Requirements**: In some projects and organizations, commit signatures may be mandatory to comply with legal or regulatory requirements, particularly for projects involving sensitive data or high-security applications.

5. **Code Review and Accountability**: Signed commits provide accountability during code reviews, ensuring that the author of each change can be easily identified. This encourages responsible development practices.

Despite the fact that GitHub has provided straightforward guides and tools to set up your commit signature, I had difficulty setting up my commit signature because of the order in which the steps had been organised in the documentation.

I have listed the doc sources in the order I find clear and concise:

1. [Generate a GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)
    
2. [Add the GPG key to your GitHub account](https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-gpg-key-to-your-github-account).
    
3. [Tell Git about your GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key).

Follow them in that order and you will not encounter any problems.

To sign your commits, you need to run the `git commit` command like this:

```bash
$ git commit -S -m "Commit Message"
```

However, to customize the command and make it easier to remember or quicker to type, learn how to create a permanent alias.