# Lager Email Backend

This is a backend for the Lager Erlang logging framework.

[https://github.com/basho/lager](https://github.com/basho/lager)

It will send all of your logging messages to the exchange you specify and use the logging level 
as the routing key. It uses a smart connection pool to your broker. If the connection drops or h
becomes unusable, the backend will reconnect.

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
    
