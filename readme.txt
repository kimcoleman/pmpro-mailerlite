=== Paid Memberships Pro - MailerLite Add On ===
Contributors: strangerstudios, flintfromthebasement
Tags: pmpro, mailerlite, email marketing, membership, sync
Requires at least: 5.6
Tested up to: 6.7
Requires PHP: 7.4
Stable tag: 0.1
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Sync your PMPro members with MailerLite groups.

== Description ==

This plugin integrates Paid Memberships Pro with MailerLite using the MailerLite API. Automatically add members to MailerLite groups based on their membership level.

= Features =

* **Simple API Key Authentication** — Just paste your API key from the MailerLite dashboard.
* **Group Management** — Assign MailerLite groups to each membership level. Members are automatically added when they gain a level and optionally removed when they lose it.
* **Double Opt-In Support** — Honor your MailerLite account's double opt-in setting so new subscribers confirm by email, or set them to active immediately.
* **Profile Sync** — Optionally sync subscriber data when a user updates their WordPress profile.
* **Background Processing** — Uses PMPro Action Scheduler for non-blocking sync operations.
* **Developer Friendly** — Filter hooks for customizing subscriber data.

= Hooks =

* `pmpromailerlite_subscriber_data` — Modify subscriber data before sending to MailerLite.
* `pmpromailerlite_controlled_group_ids` — Filter which MailerLite group IDs are managed by PMPro and eligible for removal.
* `pmpromailerlite_log_file_path` — Filter the path to the debug log file.

== Installation ==

1. Upload the `pmpro-mailerlite` folder to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Navigate to Memberships > MailerLite in your WordPress admin.
4. Enter your MailerLite API key (found under Integrations > MailerLite API in your MailerLite dashboard).
5. Save settings and configure groups for each membership level.

== Frequently Asked Questions ==

= Where do I get my API key? =

1. Log in to your MailerLite account.
2. Go to Integrations > MailerLite API.
3. Click "Generate new token".
4. Copy the token into the plugin settings.

= What are MailerLite groups? =

Groups in MailerLite are equivalent to lists or audiences in other email marketing tools. They are the primary way to organize and segment your subscribers. This plugin maps PMPro membership levels to MailerLite groups.

= Does this sync existing members? =

The plugin syncs each member when their membership level changes or when they update their profile, so your audience self-populates over time. There is no built-in bulk sync for members who already exist. To add your current members all at once, export your Members List (Memberships > Members) to a CSV and import it into MailerLite.

= Does this work with MailerLite double opt-in? =

Yes. The Subscriber Status setting controls this. Choose "Respect account settings" (the default) to honor your MailerLite account's double opt-in configuration — new subscribers receive MailerLite's confirmation email before they are subscribed. Choose "Always set to Active" to subscribe members immediately and bypass double opt-in.

= What happens when a member cancels? =

Depending on the "Remove Groups When Membership Changes" setting, the member is removed from the MailerLite groups associated with the level they lost. Groups you assign manually in MailerLite are preserved.

== Changelog ==

= 0.1 - 2026-06-21 =
* Initial release.
* MailerLite API integration with Bearer token authentication.
* Group assignment per membership level.
* Subscriber status control with MailerLite double opt-in support.
* Background sync via PMPro Action Scheduler.
* Profile update sync (configurable).
* Debug logging.
