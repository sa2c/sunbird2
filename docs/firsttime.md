# First-time login to SUNBIRD2

## Before you start

You will need:

- Your Supercomputing Wales username.
- Your existing Supercomputing Wales password.
  If you previously used SUNBIRD,
  this has been migrated to SUNBIRD2 by the technical team.
- An authenticator app,
  such as Microsoft Authenticator or Google Authenticator.

If you have previously registered an SSH public key on SUNBIRD,
this has also been migrated to SUNBIRD2 by the technical team.

### Passwords

SUNBIRD2 passwords must be at least 12 characters long.
Although advised,
there is no requirement to include a particular mix of
uppercase letters, lowercase letters, numbers or special characters.
This approach is consistent with current [NIST guidance][nist],
particularly when passwords are used alongside multi-factor authentication.

If your existing password does not meet the Sunbird2 password policy,
you will be asked to change it after completing MFA enrolment.

## Connect to SUNBIRD2

!!! important
    ## Do not use PuTTY for your first login

    Sunbird2 deliberately disconnects you when MFA enrolment is complete.
    PuTTY will close the entire session window when this happens,
    which will cause your emergency scratch codes to disappear
    before you have saved them.
    For the first login, use Windows Terminal, Command Prompt or PowerShell on Windows,
    or the normal Terminal application on macOS/Linux.

    These codes are useful if you need to access the HPC environment
    but do not have access to your authenticator application.
    Each code can be used once.
    If all codes are exhausted,
    new ones can be created.

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

## Complete MFA enrolment

On your first login,
Sunbird2 will guide you through MFA enrolment.

1. Press Enter when prompted to begin MFA enrolment.
2. Scan the QR code using your authenticator app.
3. Enter the verification code shown by the app.
4. Save the emergency scratch codes somewhere secure when they are displayed.

!!! note
    ## Keep your MFA information private
    Do not share or send
    your QR code, MFA secret key, authenticator codes or emergency scratch codes.
    Store the emergency codes somewhere secure,
    such as a password manager.

!!! note
    ## macOS

    On macOS,
    the default Terminal.app and SF Mono font
    will display blank space between each line,
    making the QR code more difficult to scan.
    If you have difficulty,
    try zoom in and out or changing to a different terminal font.

## Expect to be disconnected

When enrolment is complete,
Sunbird2 will disconnect you automatically.
This is expected and does not mean that enrolment has failed.

### Wait 20 minutes before reconnecting

After MFA enrolment,
please wait 20 minutes before trying to log in again.
SUNBIRD2 needs time for the account automation
to move your account from MFA pending to MFA enrolled and to create your Slurm associations.
Logging in again too soon may fail even though enrolment completed successfully.

## Log in normally

After waiting 20 minutes,
connect again using the same SSH command.
At this point,
you can use PuTTY or any other SSH client if you wish.

```shell
ssh s.your.username@login.sunbird.swansea.ac.uk
```

You will then complete the normal login process, including MFA verification.

## Summary: Passwords and SSH keys

- Existing SUNBIRD passwords have been migrated to SUNBIRD2
- Existing SSH public keys registered on SUNBIRD have been migrated
- If your existing SUNBIRD password does not meet the new SUNBIRD2 requirements,
  SUNBIRD2 will ask you to choose a new one.

## Getting help

Please [get in touch with support](support.md) if:

- Your password does not work
- MFA enrolment fails
- You lose access to your authenticator or emergency codes
- Your SSH key is not recognised
- You still cannot log in after waiting 20 minutes following MFA enrolment.
- You exhaust all of your emergency scratch codes and require new ones to be created

[nist]: <https://pages.nist.gov/800-63-4/sp800-63b.html>
