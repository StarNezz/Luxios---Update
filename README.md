# Luxios Bridge updates

Signed extension distribution metadata for Luxios Bridge, add-on ID `luxios-firefox@starnezz.lx`.
Endpoint: https://raw.githubusercontent.com/StarNezz/Luxios---Update/main/updates.json.

The initial update list is empty. Do not add an installable version until its selected Mozilla-signed
XPI release asset is published, anonymously accessible over HTTPS, and matches the advertised SHA256.
Never advertise an unsigned XPI or source ZIP as an installable update. No native host, credentials,
browser profile, or AI-provider config belongs in this repository.

Install the Mozilla-signed 1.4.1 bootstrap normally in Firefox on the same profile, keeping the same
extension ID. Older versions without update_url need this one manual update. Avoid uninstalling solely
to update, as that may reset grants/preferences. Firefox's automatic-update settings still apply.

Future selected signed assets use tag `vVERSION` and name `Luxios-Bridge-VERSION-signed.xpi` in this
repository's GitHub Releases. Metadata entry fields: `version`, `update_link` pointing to that exact
versioned release asset, and `update_hash` set to `sha256:` plus its actual lowercase 64-digit hash.
Do not silently replace versioned assets. Check ID/version/update_url and bounded safe package contents;
signature markers alone are not cryptographic proof. Firefox validates Mozilla's signature at install.

Publication does not prove that Firefox updated successfully. Test with an installed signed bootstrap
and a higher signed release before making that claim.

Official guidance: [Updating your extension](https://extensionworkshop.com/documentation/manage/updating-your-extension/).
