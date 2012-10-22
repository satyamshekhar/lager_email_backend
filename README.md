# Lager Email Backend

This is a backend for the Lager Erlang logging framework.

[https://github.com/basho/lager](https://github.com/basho/lager)

This backend will send all your logs to the configured email
addresses. Specially useful for warning/errors logs. You can throttle
the number of emails received per min. Setting the limit to 0, disables
throttling.

### Usage

Include this backend into your project using rebar:

    {lager_email_backend, ".*", {git, "https://github.com/satyamshekhar/lager_email_backend.git", "master"}}

### Configuration

You can pass the backend the following configuration (shown are the defaults):

    {lager, [
      {handlers, [
        {lager_email_backend, [
            {level, warning}, 
            {from, "<from.email.id@service.com>"},
            {to, ["<recpt-id1@gmail.com>", "<recpt-id2@domain.com>"]},
            {username, "someone@someservice.com"},
            {password, "hidden_pass"},
            {smtp_server, "smtp.someserver.com"},
            {emails_per_min, 10}
        ]}
      ]}
    ]}
