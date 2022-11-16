# Enterprise VPN Deployment Guide for macOS and iOS devices

This guide describes how to deploy [VPN Tracker](https://www.vpntracker.com?utm_source=github&utm_medium=web&utm_campaign=mdmconfig), an enterprise-ready VPN solution for Mac, iPhone and iPad devices with support for the following VPN protocols:
- IPsec
- L2TP (macOS)
- OpenVPN
- PPTP (macOS)
- SSTP
- AnyConnect SSL
- Fortinet IPsec and SSL
- SonicWall IPsec and SSL
- WireGuard®

The best corporate network security practises need to 

# Enterprise Rollout
There are several ways to roll VPN Tracker out to your organization. This guide you through the steps for our recommended option. Please reach out to our team, report an issue or open a pull request if you have any questions.

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

## How to create your Boarding Profile

#### Using a Profile Editor
You can use a Configuration Profile editing tool, e.g. Profile Creator or iMazing Profile Editor to create a custom Boarding Profile for your team.

We offer a Profile Manifest file that can be used with compatible Config Profile editors:

[Get the Profile manifest file](/manifest)

#### Using your MDM solution
If you MDM solution supports importing a payload, you can [download a ready-made payload from my.vpntracker](https://my.vpntracker.com/team/details).
For MDM solutions that support manual key / value entry, you can find our supported key reference below:

### Configuration Profile Reference
| Key  | Description  | Notes  |  Type |
|---|---|---|---|
| PayloadType | Mac: com.vpntracker.365mac iOS: com.vpntracker.next |  | `String` |
| Managed_Onboarding_TeamAPIToken  | The team's API Token | Find yours at [https://my.vpntracker.com/teamprofile](my.vpntracker.com/teamprofile)  | `String` |
| Managed_Onboarding_EmailDomains  | A comma-separated list of email domains that users are allowed to use when joining your team  | `yourcompany.example.com, subdomain.example.com, *.yourcompany.example`  | `String`  |
| Managed_Onboarding_Greeting|A message to display to users in the first welcome screen. | Example: "Any questions? Join #internalservices on the company Slack" | `String`|
| Managed_Onboarding_Email | The email address the user will use to sign in to VPN Tracker, when deploying a personalized profile. Enter a placeholder for the user's email address provided by your MDM solution. |   | `String` |
| Managed_Onboarding_GivenName | Used in the onboarding greeting and during VPN Tracker account registration for new users. |   | `String` |
| Managed_Onboarding_FamilyName | Used in the onboarding greeting and during VPN Tracker account registration for new users. |   | `String` |
| Managed_Onboarding_FullName|Used in the onboarding greeting.|   | `String` |

## Deploying apps
We offer the following ways of installing VPN Tracker for Mac:
- [Zip file](https://www.vpntracker.com/goto/gh/vpntenterpriseinstaller)
- [macOS Installer Package](https://www.vpntracker.com/goto/gh/vpntenterpriseinstaller)
- Homebrew: ` brew install vpntracker`

## Team Discovery and Email Domain Capture
Add your organization's domain to your VPN Tracker team to suggest your team to users signing up with associated email addresses. Team managers will receive an email to manually approved signup requests.

## Self-service signup Link
You can also post your [Team's signup link](https://my.vpntracker.com/team/details), e.g. on an internal webpage so employees can sign up without needing an invite. Team managers will receive an email to manually approved these signups.
