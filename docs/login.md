# Logging in to SUNBIRD2

<!-- 
Open OnDemand is NOT YET ENABLED.

There are two primary ways to access SUNBIRD2:

1. Command-line login over SSH (available anywhere)
2. Graphical login via Open OnDemand (campus and VPN only) -->

## Login via SSH

Using a terminal,
run

```shell
ssh s.your.username@login.sunbird.swansea.ac.uk
```

where `s.your.username` is replaced by your Supercomputing Wales username.
See [Getting access](access.md) if you don't know what this is.

When prompted,
type your Supercomputing Wales password,
and press Enter.
(You will not see characters appear on the screen as you do this.)

Then,
when prompted,
type the six-digit authentication code from your authenticator app,
and press Enter.
(You will not see characters appear on the screen as you do this.)

### Locked out?

If you repeatedly try to log in unsuccessfully
(for example,
you type the wrong password,
or cancel logging in before submitting your password),
then the system may lock you out.
This will automatically reset after a few hours;
if you need access more quickly,
please raise a ticket with the [Supercomputing Wales service desk][scw-ticket].
To allow the support desk to assist as quickly as possible,
please include [your IP address][whatsmyip] in your request.

<!--
## Login via Open OnDemand

On the campus network or VPN,
visit [the SUNBIRD2 Open OnDemand home page][ondemand],
and log in with your Supercomputing Wales username and password.

Documentation on using Open OnDemand is coming soon.
-->

## File transfer

Files can be transferred

- Using `scp`, `sftp`, or `rsync` at the command line
<!-- - Using Open OnDemand -->
- Using  [WinSCP][winscp] or [FileZilla][filezilla],
  connecting to `sftp://login.sunbird.swansea.ac.uk` on port 22
  with your Supercomputing Wales username and password

[filezilla]: <https://filezilla-project.org>
[ondemand]: <http://ood.sunbird.swansea.ac.uk>
[winscp]: <https://winscp.net>
