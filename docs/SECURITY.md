# Security at Hanabi Live

Many tech comapanies have security blogs that explain how they use your data, how they protect your data, and provide a little transparency. This blog is a short attempt to provide something similar.

<br />

### Owner

The site is owned by me (Zamiel), a Hanabi enthusiast from America. It is paid for out of pocket. The site does not run any ads and is not monetized in any way.

<br />

### Code

Hanabi Live is [open-source](https://en.wikipedia.org/wiki/Open_source), meaning that [all of the code](https://github.com/Zamiell/hanabi-live) is publicly available to review on [GitHub](https://github.com/). Note that open-source software is [not necessarily more secure](https://rubygarage.org/blog/open-source-software-security) than closed-source software.

<br />

### Hosting

The site is hosted on a [virtual private server](https://en.wikipedia.org/wiki/Virtual_private_server) from [vpsdime](https://vpsdime.com/). Physically, the VPS resides in Texas and is subject to US law.

<br />

### Staff

I am the only administrator for the website. This means that only I have the ability to mute users, ban users, and so forth.

In the [Hanabi Discord server](https://discord.gg/FADvkJp), any user with a "1+ Years Experience" role is considered a Discord administrator, and has the ability to delete messages, ban users, and so forth (in the Discord).

<br />

### Data

The database stores usernames, salted password hashes, the last IP that you logged on with, chat messages, private messages, and (obviously) Hanabi-related game history. The full schema for the database can be found [here](https://github.com/Zamiell/hanabi-live/blob/master/install/database_schema.sql). Furthermore, similar to other web servers on the internet, the web logs contain the IP address of every connection.

Notably, there is no [personally identifiable information](https://en.wikipedia.org/wiki/Personal_data) in the database (e.g. email addresses), which makes Hanabi Live a pretty low-priority target for an attacker looking to breach the website and harvest all of the data.

<br />

### Password Hasing

When you login to the website (or when you create a password-protected game), the client-side JavaScript [hashes](https://en.wikipedia.org/wiki/Cryptographic_hash_function) your password, transforming it to an alphanumeric string using the [SHA-2](https://en.wikipedia.org/wiki/SHA-2]) algorithm with a [salt](https://en.wikipedia.org/wiki/Salt_(cryptography)) that is [specific to the website](https://github.com/Zamiell/hanabi-live/blob/master/public/js/src/lobby/login.ts). Then, it then sends the hash to the server. This means that unlike other websites such as Google and Facebook, your real passwords are not ever sent to the server.

<br />

### Cookies

Upon logging in for the first time, the site stores your username and salted password hash in localstorage (e.g. a local [cookie](https://en.wikipedia.org/wiki/HTTP_cookie)). This is so that the next time you return to the site, it will automatically log you in.

The password chosen for a password-protected table is also stored in localstorage, but in plain-text instead of as a hash. While this is normally considered insecure, it is necessary so that users can actually see what the table password is in the "Create Game" tooltip (e.g. so that they can distribute the password to the other people joining the table).

<br />

### Google Analytics

The website reports anonymous usage data to [Google Analytics](https://marketingplatform.google.com/about/analytics/). This allows things like seeing a map of where most of the website visiters are from, or to see what the peak hours of the website are. This kind of thing is pretty standard.

<br />

### Sentry

Client errors are automatically reported to [Sentry](https://sentry.io/welcome/), a cloud-based service that aggregates errors. The username and IP address are uploaded alongside an error report. This kind of thing is pretty standard.

<br />

### Server

The virtual server runs on the latest version of [Ubuntu Server](https://ubuntu.com/download/server). It is protected by a host-based firewall. I make a best-effort to keep the machine up-to-date in terms of operating system packages, Go versions, and NPM packages.

<br />

### Trust Model

Like any other website on the internet, usage of Hanabi Live relies on an implicit trust model.

* Since Hanabi Live is hosted in America, the United States government technically has the ability to gain full control of the server under a [gag order](https://en.wikipedia.org/wiki/Gag_order). This means that members of the government could:
  1) intercept any data submitted to the website
  2) get any data from the database, and
  3) deploy any arbitrary JavaScript code, which would run on your computer when visiting
* In a similar vein, since [vpsdime](https://vpsdime.com/) has physical control of the server, the above points also apply to members of the their company.
* Since I have virtual control of the server, the above points also apply to me.
* While I do my best to harden the server and codebase as much as reasonably possible, I cannot guarantee that the site will not ever be breached by an attacker, in which case the above points would also apply to the attacker.
