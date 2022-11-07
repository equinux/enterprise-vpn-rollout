# enterprise-vpn-rollout
Documentation and how-tos on deploying VPN Tracker in organizations using configuration profiles.

## Overview
VPN Tracker is an enterprise VPN client for macOS, iOS and iPadOS. It supports the following VPN protocols:
- IPsec
- L2TP (macOS)
- OpenVPN
- PPTP (macOS)
- SSTP
- AnyConnect SSL
- Fortinet SSL
- SonicWall SSL
-  WireGuard®

# Enterprise Rollout
There are several ways to roll VPN Tracker out to your organization. This guide gives provides detailed steps for some of the options. Please reach out to our team, report an issue or open a pull request if you have any questions.

### Pre-requisites
Before you start rolling out VPN Tracker, this guide assumes that
- You already have a working VPN Tracker connection
- You have a VPN Tracker VIP license as a manager on your team
- You are familiar with Configuration Profiles for Mac or iOS devices

## Onboarding Team Members via Configuration Profiles
VPN Tracker supports a customized onboarding flow that can be set up via a Configuration Profile. 

Using the profile you can
- Display a branded onboarding screen to new users with your organization's logo and a custom message
- Pre-determine which email address new users can sign up with
- Automatically add new users to your VPN Tracker team and assign them a license and optionally add them to a specific group

Two use cases are supported

**A. Personalized Onboarding Profile with an MDM solution**
If your organization's devices are enrolled with an MDM solution, you can push a customized profile onto each user's device. 
This allows you to pre-fill the email address and personal details used to sign up for VPN Tracker, so the new user only needs to set a password.

**B. General Onboarding Profile**
You can also omit personal details from the profile, allowing you to just specify the team a user will join and optionally require their sign-up email address to be from your organization's domain.

### Configuration Profile Reference
| Key  | Description  | Example  |  Notes |
|---|---|---|---|
|  PayloadType | Mac: com.vpntracker.365mac
iOS: com.vpntracker.next  |  |  |
|   |   |   |   |   |
|   |   |   |   |   |


### Team Discovery and Email Domain Capture
Coming soon

### Self-service signup Link
Coming soon

## Deploying apps
We offer the following ways of installing VPN Tracker for Mac:
- Zip file
- macOS Installer Package
- Homebrew