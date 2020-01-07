# Enabling Remote Live Staging

In Remote Live Staging, a connection is established between the current Site and another Site on a remote Liferay server. The remote Site becomes the live environment and the local (current) Site becomes the Staging environment -- an instance of Liferay used solely for Staging. The remote (live) Liferay server and the local (Staging) Liferay server should be completely separate systems. They should not, for example, share the same database. [TODO: Is the previous sentence really true? I could see that they shouldn't be on the same server themselves, but I feel like it is not uncommon practice for them to share the same DB at least] When Remote Live Staging is enabled, all the necessary information is transferred over the network connecting the two servers. Content creators use the Staging server to make their changes while the live server handles the incoming user traffic. When changes to the Site are ready to be published, they are pushed over the network to the remote live server. 

Before enabling Remove Live Staging, ensure you've configured your Liferay server and remote server appropriately. Follow the [Configuring Servers for Remote Live Staging](/docs/7-2/user/-/knowledge_base/u/configuring-servers-for-remote-live-staging) article to do this.

## Enabling Remote Live Staging

You can enable remote Staging for a Site by navigating to the *Publishing* &rarr; *Staging* menu. Step through the instructions below to create a Remote Live Staging environment for your Site. 

1.  Navigate to the Product Menu and select *Publishing* &rarr; *Staging*.

2.  Select *Remote Live*. Additional fields appear for Remote Live Connection Settings.

    ![Figure 1: After your remote Liferay server and local Liferay server have been configured to communicate with each other, you have to specify a few Remote Live connection settings.](../../../../images/remote-live-staging-settings.png)

3.  Enter your remote Liferay server's IP address into the Remote Host/IP field. This field should match the host you specified as your `tunnel.servlet.hosts.allowed` property in the `portal-ext.properties` file. If you're configuring an IPv6 address, it must contain brackets when entered into the *Remote Host/IP* field (e.g., *[0:0:0:0:0:0:0:1]*).

    > **Note:** If the remote Liferay server is a cluster, you can set the Remote Host/IP to the load balanced IP address of the cluster to increase the availability of the publishing process. See the [Configuring Remote Staging in a Clustered Environment](/docs/7-2/deploy/-/knowledge_base/d/configuring-remote-staging-in-a-clustered-environment)
    for details.

4.  Enter the port on which the remote Liferay instance is running into the Remote Port field. You only need to enter a Remote Path Context if a non-root portal servlet context is being used on the remote Liferay server.

5.  Enter the ID of the Site on the remote Liferay server for the live environment. If a Site hasn't already been prepared on the remote Liferay server, you can log in to the remote Liferay server and create a new blank Site.

    After the Site has been created, note the Site ID so you can enter it into the Remote Site ID field on your local Liferay server. You can find any Site's ID by selecting the Site's name on the Sites page of the Control Panel.
 
6.  Check the *Use a Secure Network Connection* field to use HTTPS for the publication of pages from your local (Staging) Liferay server to your remote (live) Liferay server.

7.  If desired, enable page versioning and select staged content. For more information on these options, see the [Enabling Page Versioning and Staged Content](/docs/7-2/user/-/knowledge_base/u/enabling-page-versioning-and-staged-content) article.

8.  Click *Save*.


[TODO: look at this stuff, decide what to do with it]
You've officially begun the staging process!

If you fail to configure your current and remote server properly, you won't be
able to enable staging and an error message appears. If you have issues,
[verify you've configured your servers properly](/docs/7-2/user/-/knowledge_base/u/configuring-servers-for-remote-live-staging).

When a user publishes changes from the local (staging) server to the remote
(live) server, DXP passes the user's email address, screen name, or user
ID to the remote server to perform a permission check. For a publishing
operation to succeed, the operation must be performed by a user that has
identical credentials and permissions on both the local (staging) and the remote
(live) server. This is true regardless of whether the user attempts to publish
the changes immediately or attempts to schedule the publication for later.

If only a few users should have permission to publish changes from staging to
production, it's easy enough to create a few user accounts on the remote server
that match a selected few on the local server. The more user accounts that you
have to create, however, the more tedious this job becomes and the more likely
you are to make a mistake. And you not only have to create identical user
accounts, you also have to ensure that these users have identical permissions.
For this reason, it's recommended that you use LDAP to copy selected user
accounts from your local (staging) Liferay server to your remote (live) Liferay
server. Liferay's Virtual LDAP Server application, available on Liferay
Marketplace, makes this easy.

See the
[Disabling Staging](/docs/7-2/user/-/knowledge_base/u/disabling-staging)
article to learn how to turn off the staging environment.

Great! Now you're ready to use Remote Live Staging.
