---
layout: post
title: Managing multiple github accounts in a single machine using SSH
comments: true
tags: [self-note]
---

In this article I will be sharing how to manage multiple github accounts in a single maching using SSH.

I recently wanted to use my personal github for my own contributions, alongside contributing in my work github account, I
knew I had setup SSH for my github-work, I did follow some steps to create a public/private key, but now when I want to push in my github-personal, I get error that meant I am trying to push in my github-personal using my github-work account (for simplicity I will be calling github used for work as github-work, and for personal as github-personal).
Ideally I wanted that I am able to make a switch between the two without switching to a different system and with super ease.

There is one way that, the usual way I could have done, i.e using https, for this I had to generate Personal Access token, which github recently switched to from the previous method of using github username and password. This can be referred [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

Reason I chose not to go ahead with this method:
- Overhead of saving this access token, thereby making it vulnerable of getting lost.
- secondly, using ssh is a much secure way of authentication.

So, to setup I did follow the below steps:
- Create a new secret key and store it in a seperate file, [refer here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)
- Add this to the Github Account [refer here](https://docs.github.com/en/enterprise-server@3.0/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
- Register the key with the ssh agent [refer here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)
- Edit .gitconfig, so as to tell git which key to use in particular scenario, something like this
    ```git
    [includeIf "gitdir:<directory to whitelist all personal repos>"]
        [user]
            name = <your name>
            email = <your github email>
        [core]
        sshCommand = "ssh -i <ssh key path of github-personal>"

    ...
    rest details of the other (work) account
    ...
    ```
- Also make sure to set username and email local to this repository
    ```git
        git config user.name = <your name>
        git config user.email = <your github email>
    ```

Refernce Posts:
- https://dev.to/arnellebalane/setting-up-multiple-github-accounts-the-nicer-way-1m5m
- https://gist.github.com/jexchan/2351996

With these simple steps, we will be able to setup github-work/personal and switching between them securely and with ease.
Hope it helped!!
