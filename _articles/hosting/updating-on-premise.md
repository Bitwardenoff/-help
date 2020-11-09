---
layout: article
title: Updating your self-hosted installation
categories: [hosting]
featured: false
popular: false
tags: [hosting, update]
---

It is very important to keep your Bitwarden installation up to date. Updates may include fixes that are important for the security of your Bitwarden installation. Additionally, newer versions of client applications such as the browser extension and/or mobile apps may not support older versions of your self-hosted Bitwarden server.

We have made updating your Bitwarden installation very simple. Use the same Bitwarden Bash (macOS and Linux) or PowerShell (Windows) script that you obtained while installing Bitwarden to your server to update your Bitwarden installation. Run the following sequence of commands:

{% icon fa-linux %} {% icon fa-apple %} Bash

    ./bitwarden.sh updateself
    ./bitwarden.sh update

{% icon fa-windows %} PowerShell

    .\bitwarden.ps1 -updateself
    .\bitwarden.ps1 -update

Your Bitwarden installation should now be fully up to date and running.

{% callout success %}
Create a cronjob or scheduled task to run these update commands weekly, or even nightly. This will automatically keep your installation up to date.
{% endcallout %}
