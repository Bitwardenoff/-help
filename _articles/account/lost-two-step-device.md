---
layout: article
title: I lost my two-step login (2FA) device
categories: [account-management]
featured: false
popular: false
tags: [two-step login, 2fa, two factor authentication, account]
---

If you have lost access to the device or method that you use for two-step login (2FA) you can recover your account using your two-step login **recovery code**.

The recovery code is a 32 character alpha-numeric code. You can get your two-step login recovery code in the [web vault](https://vault.bitwarden.com) under **Settings** &rarr; **Two-step Login**, then click the **View Recovery Code** button. We recommend that your print your recovery code and keep it in a safe place.

{% warning %}
Without your recovery code, two-step login can permanently lock you out of your Bitwarden account. It is very important to have your recovery code if you plan to use two-step login. Bitwarden support will not be able to assist you if you lose access to your account.
{% endwarning %}

{% tip %}
If you still have an active login session open in the browser extension or a mobile application you can export your data from **Tools** &rarr; **Export Vault** so that you can import it back in after the account has been deleted and you have registered again.
{% endtip %}

## Recovering Your Account

Please use this link to enter your 2FA recovery code: <https://vault.bitwarden.com/#/recover-2fa>

The recovery process will deactivate two-step login on the account so that you can log in without requiring the normal two-step login verification code. You will need to re-enable two-step login in the web vault if you wish to continue using it after recovering the account.

{% warning %}
The recovery process also resets your account's recovery code. Make sure that you take note of your new recovery code when re-enabling two-step login.
{% endwarning %}

If you do not have your recovery code, unfortunately there is no way to fully recover the account. The only option to gain access to the account again is to delete the account so that you can register again and start over. Note that deleting the account will also delete all of your stored login data associated with the account.

## Deleting the account

1. Navigate to <https://vault.bitwarden.com/#/recover-delete>
2. Enter your account's email address
3. Go to your email inbox and click the verification link that was sent to you
4. Confirm the delete

You can now register a new account using the same email address. If you have an active subscription use our [contact page](https://bitwarden.com/contact/) to let us know, and we will re-instate it to your newly created account.