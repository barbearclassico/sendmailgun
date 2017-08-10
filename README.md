# sendmailgun

Mail relay using sendmail and mailgun

## Setup mailgun and DNS.

ditto

## Install

1. Append configuration to sendmail.mc


    ## Mailgun
    define(`SMART_HOST', `smtp.mailgun.org')dnl
    FEATURE(`authinfo', `hash /etc/mail/authinfo/mailgun-auth')dnl
    # optional, see http://www.sendmail.org/m4/features.html before enabling:
    # FEATURE(`accept_unresolvable_domains')dnl
    # FEATURE(`accept_unqualified_senders')dnl
    # execute: make -C /etc/mail
    ## Mailgun
    MAILER_DEFINITIONS
    MAILER(`local')dnl
    MAILER(`smtp')dnl


1. Create the authentication file at `/etc/mail/authinfo/mailgun-auth`
1. run `make authinfo`


## Testing

Send a mail with the command

    echo "Mail body" | mail  -s "Mail subject" to@mail.com

Check local mail/logs for errors
