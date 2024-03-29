The google-authenticator PAM module has been moved to https://github.com/google/google-authenticator-libpam/.

Build & install by running:

    ./bootstrap.sh
    ./configure
    make
    make install

If you don't have access to `sudo`, you have to manually become "root" prior
to calling `make install`.

Then add this line to your PAM configuration file:

```
auth required pam_google_authenticator.so
```

Run the `google-authenticator` binary to create a new secret key in your home
directory.

If your system supports the "libqrencode" library, you will be shown a QRCode
that you can scan using the Android "Google Authenticator" application. If your 
system does not have this library, you have to manually enter the alphanumeric
secret key into the Android "Google Authenticator" application. In either case,
after you have added the key, click-and-hold until the context menu shows. Then
check that the key's verification value matches.

Each time you log into your system, you will now be prompted for your TOTP code
(timebased one-time-password) after having entered your normal user id and your
normal UNIX account password.

For more details, see the [README](https://github.com/google/google-authenticator-libpam/blob/master/README.md).