The Google Authenticator project includes implementations of one-time passcode generators for several mobile platforms, as well as a pluggable authentication module (PAM). One-time passcodes are generated using open standards developed by the [Initiative for Open Authentication (OATH)](http://www.openauthentication.org/)  (which is unrelated to [OAuth](http://oauth.net/ OAuth)). 

These implementations support the HMAC-Based One-time Password (HOTP) algorithm specified in [RFC 4226](https://tools.ietf.org/html/rfc4226) and the Time-based One-time Password (TOTP) algorithm specified in [ RFC 6238](https://tools.ietf.org/html/rfc6238).

Index
=====

* [[Checking Out]]
* [[BlackBerry Development]]
* [[Conflicting Accounts]]
* [[Key Uri Format]]
* [[Pam Module Instructions]]
* [[Troubleshooting Tips]]

Implementations
===============

This project currently offers mobile application implementations of HOTP/TOTP for [Android](http://www.android.com/), iOS, and Blackberry, as well as a PAM module.

Google Authenticator for Android
================================

The code for Android has been moved to [a separate GitHub project](https://github.com/google/google-authenticator-android).

The [Android mobile app](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2) supports:

  * Multiple accounts
  * Support  for 30-second TOTP codes
  * Support for counter-based HOTP codes
  * Key provisioning via scanning a QR code
  * Manual key entry of [RFC 3548](http://tools.ietf.org/html/rfc3548) base32 key strings

*DISCLAIMER*: This open source project allows you to download the code that powered version 2.21 of the application.  Subsequent versions contain Google-specific workflows that are not part of the project.

Google Authenticator for iOS
============================

The [iOS mobile app](http://itunes.apple.com/us/app/google-authenticator/id388497605?mt=8) supports:

  * Multiple accounts
  * Support  for 30-second TOTP codes
  * Support for counter-based HOTP codes
  * Key provisioning via scanning a QR code
  * Manual key entry of [RFC 3548](http://tools.ietf.org/html/rfc3548) base32 key strings

Google Authenticator for Blackberry
===================================

The BlackBerry mobile app supports:

  * Multiple accounts
  * Support for 30-second TOTP codes
  * Support for counter-based HOTP codes
  * Manual key entry of [RFC 3548](http://tools.ietf.org/html/rfc3548) base32 key strings

PAM Module
==========

The [PAM module](https://github.com/google/google-authenticator/tree/master/libpam) can add
a two-factor authentication step to any PAM-enabled application. It supports:

  * Per-user secret and status file stored in user's home directory
  * Support for 30-second TOTP codes
  * Support for emergency scratch codes
  * Protection against replay attacks
  * Key provisioning via display of QR code
  * Manual key entry of [RFC 3548](http://tools.ietf.org/html/rfc3548) base32 key strings

Source Code
===========

You can checkout the project's source code from the Git repository. See more details in CheckingOut.