The vast majority of problems with TOTP two-step verification are a
direct result of the server and the token-generator having different
ideas of what the current time is. Some amount of time skew is tolerated.
But significant differences will usually result in two-step verification failing.

The PAM module has an optional feature to detect and compensate for
excessive skew in time stamps. If enabled, if requires the user to
repeatedly try to log in. After a sequence of three successful tokens
the PAM module learns the client's time skew and will subsequently
compensate for it. See the [README](https://github.com/google/google-authenticator/blob/master/libpam/README.md) file for details.

But sometimes interactive debugging tools are more helpful in tracking
down problems. For this purpose, you can use the interactive
[TOTP debugger](https://raw.githubusercontent.com/google/google-authenticator/master/libpam/totp.html). And you can also run the [demo.c](https://github.com/google/google-authenticator/blob/master/libpam/demo.c,) program to see if your
token would be accepted by the server.