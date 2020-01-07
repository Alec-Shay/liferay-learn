# Disabling Staging

[TODO: this intro section could all probably be stated better...]
Disabling Staging doesn't take a lot of steps, but should not be done lightly. It's important to know the consequences of turning the Staging environment off so you can decide if your circumstances really warrant it.

The consequences for disabling Local Live and Remote Live Staging are slightly different, so you'll learn about both.

## Disabling Local Live Staging

The live Site is the final approved version of your Site, whereas the Staging Site is a temporary workspace containing information that is not finalized.

Disabling local Staging completely removes the staging environment, which means all content not published to your live Site is erased. Before disabling Staging, you must ensure all necessary information on the staged Site is published or preserved elsewhere.

Keep in mind that draft content types are not published, so they can be lost too.

When you enable Staging, there is an initial publication. Disabling Staging does not start a publication; the Staging Site is deleted. If the Staging Site contains a large amount of content, however, those deletions could take a substantial amount of time to process. For this reason, don't disable Staging when your DXP instance is busy.

## Disabling Remote Live Staging

Disabling remote Staging does not delete the Staging Site; it only disables the connection between the live Site and remote Staging Site. This means no data is deleted from the live or remote Staging Sites after the connection is disabled. Since no data is erased and no processes are started, disabling remote Staging is almost instantaneous.

When Remote Live Staging is enabled, certain information (e.g., which portlet is being staged) is recorded on both the live and Staging Sites. For this reason, when you disable remote Staging, you must ensure the live Site is still accessible so both sides can communicate that it's disabled. Do not shut down your live Site and then attempt to disable remote Staging from your Staging Site; this results in errors.

### Forcibly Disabling Remote Live Staging

If there's ever a lost network connection between the remote Staging Site and the live Site, a message appears, informing you of the error and a way to forcibly disable staging. This is only an option for the staged site; executing this option erases the Staging Site's Staging information (not the content).

At the same time, the live Site remains in a locked state, since it could not be informed that Staging was disabled. A possible workaround is to create a new live Site and import content to it, if necessary.

## Steps to Disable Staging

Follow the steps below to disable Local Live or Remote Live staging:

1.  Navigate to the *Publishing* &rarr; *Staging* option, which is only
    available from the staged site.

2.  Click the *Options* icon (![Options](../../../../images/icon-options.png)) from the upper right corner of the page and select *Staging Configuration*.

3.  Select the *None* radio button and click *Save*.

That's it! Your Staging environment is now turned off.
