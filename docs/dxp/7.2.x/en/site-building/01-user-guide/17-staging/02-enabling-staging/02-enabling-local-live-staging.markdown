# Enabling Local Live Staging


[TODO: should this explanation be moved into an intro/overview article somewhere? Or at least part of it should be there too....]
Local Live staging places both your Staging environment and your live environment on the same server. When it's enabled, a clone of the Site is created containing copies of all of the Site's existing pages. This means the Staging and live environments share the same JVM, database, portlet data (depending on which portlets are selected when staging is enabled), and configurations, such as the properties set in the `portal-ext.properties` file. The cloned Site becomes the Staging environment and the original Site becomes the live environment.

## Steps to Enable Local Live Staging

Enable local Staging for a Site from the Site's *Staging* menu. Follow these steps to create a Local Live Staging environment for your Site:

1.  Navigate to the Product Menu mand select *Publishing* &rarr; *Staging*.

2.  Select *Local Live*. You can also enable page versioning and select staged content. For more information on these options, see the [Enabling Page Versioning and Staged Content](/docs/7-2/user/-/knowledge_base/u/enabling-page-versioning-and-staged-content) article.

3.  Click *Save*.

You've officially begun the Staging process!

Because Local Live Staging creates a clone of your Site, It is recommended to only activate Staging when a Site is new or does not have much content, because Sites with a large amount of content can take a long time to copy when the Site is cloned for the Staging environment.

Additionally, if you intend to use page mversioning to track the history of updates to your Site, you should enable it as early as possible, *before* your Site has many pages and a lot of content. Your Site's update history isn't saved until you enable page versioning. Page versioning requires Staging (either Local Live or Remote Live) to be enabled.

If you ever need to turn off the Staging environment, return back to *Staging* from the Publishing dropdown. For more information on this, see the [Disabling Staging](/docs/7-2/user/-/knowledge_base/u/disabling-staging) article. Take care to note that doing so will delete the Staging environment, unlike with disabling remote Staging.

[TODO: in our heart of hearts is this really a good line to have]
Great! Now you're ready to use Local Live Staging.
