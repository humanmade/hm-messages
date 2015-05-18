hm-messages
===========

A simple error / success messages API for WordPress

hm-messages provides an API to send / display success or failure messages in a WordPress theme or wp-admin. Each message is only shown once to the user; hm-messages uses cookies to pass messages between page reqyuests.

To send a message:

```
hm_error_message( 'Please enter a title' );
```

To then display any messages, place the following whereever you want the messages to show:

```
hm_the_messages();
```

Messaging also supports contexts so it is possible to show different messages in different places. For example, to display messages to do with login above a login form:

```
hm_success_message( 'You have been emailed your password', 'login' );
```

And output `login` messsages:

```
hm_the_messages( 'login' );
```

### Functions

```
hm_error_message( $message, $context ); // display an error message
hm_success_message( $message, $context ); // display an success message

hm_the_messages( $context ); // display all messages (optionally from a given context)
hm_get_the_messages( $context ); // get all messages as a html string (optionally from a given context)

hm_get_messages( $context, $clear_messages = true ); // get the messages as an array, optionally clearing the messages once retreived
```

### Gotcha's

You must have a call to `wp_footer` in your theme's `footer.php`.

Styling for messages is not provided, style `.message.error` and `.message.success` in your theme's CSS file.

## Contribution guidelines ##

see https://github.com/humanmade/hm-messages/blob/master/CONTRIBUTING.md
