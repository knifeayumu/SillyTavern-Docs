---
label: Single Sign-On (SSO)
icon: key
order: -20
---

# Single Sign-On (SSO)
SSO allows you to create users and secure many different pages using a login portal presented on sites you want to secure. While it is complex to setup, it is a good way to both learn SSO and secure your ST instance out on the internet more.

[**Authelia**](https://www.authelia.com/) and [**Authentik**](https://goauthentik.io/) are open-source SSO providers that can be used with SillyTavern. 

## Sign in with SSO

If your SSO-provided username exactly matches the username of a SillyTavern user account, you can sign in to SillyTavern as that user by SSO.

To do this, enable `autheliaAuth` in *config.yaml*.
    
```yaml
autheliaAuth: true
```

This augments or replaces the built-in [password management](/Usage/User_Settings/User_Settings.md#account-management) component of a [multi-user mode](/Administration/multi-user.md) setup.

## Replacing HTTP BA

SSO can also replace [HTTP Basic Authentication](/Administration/remote-connections.md#access-control-by-http-basic-authentication) as an access control mechanism for [remote connections](/Administration/remote-connections.md#access-control).

This is recommended because SSO provides better security and functionality than HTTP BA.

To use an SSO provider in place of HTTP BA, enable `securityOverride` in *config.yaml*. Otherwise, SillyTavern will [refuse to start](remote-connections.md#access-control).

```yaml
autheliaAuth: true
basicAuthMode: false
securityOverride: true
```
