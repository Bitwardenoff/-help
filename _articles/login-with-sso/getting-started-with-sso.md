---
layout: article
title: Getting started with Login with SSO
categories: [login-with-sso]
featured: true
popular: false
tags: [sso, saml, oidc, openid, saml2.0, idp, identity]
---

## What is Login with SSO?

The Login with SSO feature allows you to use your existing Identity Provider to authenticate into Bitwarden. Login with SSO is available on the current Enterprise Plan.

### Identity Server Requirements
- Support for SAML 2.0
- Support for OpenID Connect

### Bitwarden API/ Server Requirements
- Bitwarden Cloud services
- Self-hosted Bitwarden Server v1.37+

### Client requirements
- Desktop version 1.21+
- Browser extension version 1.46+
- Mobile version 2.6+
- Web version 2.16+
- CLI version 1.12+  (CLI applications leveraging Login with SSO must run on systems with an available web browser)

## Workflow

{%image /sso/sso-workflow.png Overview of Bitwarden Single Sign-On Workflow %}

## General settings and configuration
To enable Login with SSO, you’ll need to log into the Bitwarden Web Vault and access your Organization.

### Organization Identifier
When enabling Login with SSO, you’ll create an organization identifier, unique to your organization, that will allow the client to identify and connect to the right identity servers. This will be entered upon login.

Define the Organization Identifier inside the Organization Vault: Settings > My Organization.

{%image /sso/sso-orgid.png Overview of Bitwarden Single Sign-On Workflow %}

Once you have created your Organization Identifier from the Organization Settings page, you’ll
select the link to the Business Portal.

{%image /sso/sso-business-portal.png Enter the new Business Portal to manage Organization settings %}

Within the Business Portal, you’ll see the option to enable and configure Login with SSO.

{%image /sso/sso-select.png Select your protocol %}

Click the checkbox to enable Single Sign-On and select the protocol for your Identity Provider.

{%note%}
Depending on your Identity Provider and configuration, you may need to perform the creation of an additional API key or Application ID within the Identity service prior to enabling and configuring your Bitwarden Organization.

We recommend you maintain a distinct application ID or reference for Bitwarden within your Identity Server.
{%endnote%}

### SAML 2.0 Configuration

Bitwarden Login with SSO is configurable to work with your SAML 2.0 IdP - for details on configuration please use [this article.](https://bitwarden.com/help/article/configure-sso-saml/)

{%image /sso/sso-saml.png SAML 2.0 Configuration Options %}

### Open ID Connect (OIDC) Configuration

Bitwarden Login with SSO is configurable to work with your OIDC IdP - for details on configuration please use [this article.](https://bitwarden.com/help/article/configure-sso-oidc/)

{%image /sso/sso-oidc.png Open ID Connect Configuration Options %}

## Logging In with SSO

Logging into your Bitwarden client using Login with SSO is accomplished by a few steps.

1. Once your Bitwarden client app is installed, navigate to the login screen or window.
2. Click or tap the **Enterprise Single Sign-On** button.
3. Enter your Organization Identifier.
4. A browser window will open, allowing you to enter your Single-Sign-On credentials and any other required authentication mechanisms.
5. Upon successful login:
- For existing accounts, you will be brought back into the Bitwarden application and prompted for your Master Password.
- For new accounts, you will be prompted to create your Master Password and provide a password hint if desired.
- The user is now logged into their Bitwarden account and is in *accepted* status within their organization.

{%note%}
Users that register “Just-In-Time” or “on the fly” for their Organization will still need to be confirmed to access any shared Organization Items. For more information about managing and confirming users, visit our article [here.](https://bitwarden.com/help/article/managing-users/)

Users will also need to be assigned to any Groups and Collections.

Users that are created via Login with SSO **will still be properly organized into their groups and collections** if leveraging the [Directory Connector.](https://bitwarden.com/help/article/directory-sync/) utility.
{%endnote%}

## FAQs

**Q: What Plans offer Login with SSO?**

**A:** Current Enterprise plans offer this feature. To upgrade from a Classic Enterprise plan to a current Enterprise offering, please [contact us](https://bitwarden.com/contact)

**Q: Will changing my SSO password affect my Master Password?**

**A:** No, your Master Password will remain the same unless changed within the web Vault.

**Q: Will this work with a self-hosted instance of Bitwarden?**

**A:** Yes! It will work with self-hosted regardless of whether it is on-premise or in your own cloud, as long as your Identity server is reachable from the Bitwarden instance.

**Q: Do I still need to use Bitwarden Directory Connector?**  

**A:** If you manually manage your Bitwarden Group and Collection assignments, there is no need to leverage the Directory Connector. However, if you would like to have Groups and users automatically synchronized, we recommended leveraging Login with SSO with Directory Connector for the most complete solution.
