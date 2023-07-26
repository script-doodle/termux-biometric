# Add Fingerprint Authentication to Termux

Welcome to the comprehensive guide on how to integrate fingerprint authentication into Termux, the popular terminal emulator for Android. With this step-by-step tutorial, you'll learn how to implement fingerprint-based security within your Termux environment, adding an extra layer of protection to your sensitive data and commands.

This guide aims to provide clear and concise instructions, accompanied by code snippets and necessary dependencies, to make the process seamless for both beginners and experienced users. By following this guide, you'll be able to leverage the power of fingerprint authentication in Termux, enhancing your overall mobile security and privacy.

Whether you're a developer, a tech enthusiast, or someone looking to bolster their Android terminal security, this guide will assist you in implementing fingerprint authentication in your Termux environment quickly and effortlessly. So, let's get started and take your Termux experience to the next level of security and convenience!

## Table of Contents

1. [Prerequisites](#prerequisites)

2. [Setting up Termux Environment](#setting-up-termux-environment)

3. [Implementing Fingerprint Authentication](#implementing-fingerprint-authentication)

4. [Conclusion](#conclusion)

## Prerequisites

**1. Android Device with Fingerprint Sensor**

You'll need an Android device that has a built-in fingerprint sensor. Fingerprint authentication relies on this hardware for biometric recognition.

</br>

**2. Termux and Termux:API Installed**

Make sure you have Termux and Termux:API installed on your Android device. You can download and install them from the [Google Play Store](https://play.google.com/store/apps/details?id=com.termux) or the [F-Droid](https://f-droid.org/en/packages/com.termux/) repository (recommend).

</br>

**3. Basic Familiarity with Terminal**

While this guide aims to be beginner-friendly, having some familiarity with using the terminal or command-line interface will be helpful.

</br>

With these prerequisites in place, you're all set to follow the steps and add fingerprint authentication to your Termux environment. Let's get started!

## Setting up Termux Environment

**1.Update Termux packages to ensure you have the latest versions.**

```
pkg update; pkg upgrade -y
```

</br>

**2.Install necessary package to help your Termux authenticate.**

```
pkg install -y termux-api
```

*P.S: Don't get confused between `Termux:API` and `termux-api`*

</br>

**3.Enable storage access for biometric data.**

```
termux-setup-storage
```

## Implementing Fingerprint Authentication

**1. Bash/Zsh Shell Users**

We'll edit the `bash.bashrc` or `zshrc` file. Which are located at `../usr/etc/`

According to your shell run one of the code below to open the file in editor

```
nano ../usr/etc/bash.bashrc
```

```
nano ../usr/etc/zshrc
```

Take your cursor to the very end of editor by scrolling up or by using arrow &darr; button and paste the code below

```
if termux-fingerprint | grep -q "AUTH_RESULT_FAILURE"; then
 am stopservice com.termux/.app.TermuxService
fi
```
Then execute next few commands accordingly. `CTRL+o` to finish editing, &#9166; to save the file and `CTRL+x` to exit the editor

</br>

**2. Fish Shell Users**

We'll edit the `config.fish` file. Which is located at `../usr/etc/fish/`

Run the code below to open the file in editor

```
nano ../usr/etc/fish/config.fish
```

Take your cursor to the very end of editor by scrolling up or by using arrow &darr; button and paste the code below

```
if termux-fingerprint | grep -q "AUTH_RESULT_FAILURE"; then
 am stopservice com.termux/.app.TermuxService
end
```
Then execute next few commands accordingly. `CTRL+o` to finish editing, &#9166; to save the file and `CTRL+x` to exit the editor

## Conclusion

Restart your Termux to enjoy the Biometric authentication

## Author

- [Md Mussanna Bin Sharif Mahin](https://github.com/script-doodle)

## Acknowledgements

- [readme.so](https://readme.so/)
- [ChatGPT](http://openai.com)
