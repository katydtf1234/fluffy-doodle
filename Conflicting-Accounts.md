How to deal with conflicting accounts
=====================================

As more websites add support for 2-Step Verification using the TOTP standard, there
is an increased risk that a user will have identical profiles for two or more
different websites. For instance, user `joe_example@gmail.com` may have the same
username for many websites (including Google, Facebook, Dropbox, and Live.com).

If that user has enabled two step verification for all websites and intends to
add all of the accounts to the same code generation app, this may result (depending
on how the code generating application handles conflicting accounts internally) in
accounts that are indistinguishable to the user in the application UI, or worse yet,
in a situation where one account overwrites another, effectively locking the user
out of the overridden account.

Recommendation for websites supporting the TOTP/HOTP standard
-------------------------------------------------------------

When you encode a URI in a QR code you should make sure you add the “Issuer Parameter”
(described in the [URI format page](Key Uri Format)) to allow the code generating app
to programmatically distinguish the account from others using the same username.

Moreover, for backwards compatibility with older versions of code generating apps, we
recommend prepending the issuer name to the account label, followed by colon (:).
By adding this prefix, you will be preventing code generation applications that do not
read the `issuer` parameters from overwriting your entry.  You will also make it
easier to the end user to tell which code generator goes with your site.

For instance, if your website’s name is “Company” and the username is
`joe_example@gmail.com` consider encoding the following URI format in the QR code that
apps will read:

```
otpauth://totp/Company:joe_example@gmail.com?secret=[...]&issuer=Company
```

Note:  The label prefix will ensure that the account distinguished in any version of
Google Authenticator.  Later in Summer 2013,  Google Authenticator will provide a UI
to make use the parameters to classify accounts with different users.

Recommendation for code generation app developers
-------------------------------------------------

If you are developing a code generating app that uses the TOTP standard, we
recommend the following:

* Your code should read the issuer parameter and use it to distinguish entries.

* Ideally, your code could make use of the issuer parameter to surface branding
  in the UI.  If you encounter encoded URIs where the issuer name appears in the
  prefix as well as a URI parameter, consider stripping the issuer name in the
  UI and branding accordingly.
  
  For instance if you app reads a URI of the form,

  `otpauth://totp/Company:joe_example@gmail.com?secret=[...]&issuer=Company`

  consider surfacing the account in the UI using the label `joe_example@gmail.com`
  and brand “Company”.

* The internal logic your app needs to avoid overriding existing entries with
  the same username that belong -or might belong- to completely different websites.