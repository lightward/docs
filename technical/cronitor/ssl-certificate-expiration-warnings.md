# SSL certificate expiration warnings

We have Cronitor monitors (love that language) keeping an eye on all the spots we accept HTTP traffic. These monitors are configured to verify SSL certificates. This monitoring comes with certificate _expiration_ warnings, which can't be selectively disabled. These warnings are safe to ignore, since Fly manages our certs automatically.

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-15 at 11.22.41 AM.png" alt="" width="375"><figcaption><p>Here's how that warning looks in Slack</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image.png" alt="" width="360"><figcaption><p>Here's how the config looks in Cronitor.</p></figcaption></figure>
