# Luxios Bridge updates

Signed extension distribution metadata for Luxios Bridge, add-on ID `luxios-firefox@starnezz.lx`.
Endpoint: https://raw.githubusercontent.com/StarNezz/Luxios---Update/main/updates.json.

The update list advertises [1.4.2](https://github.com/StarNezz/Luxios---Update/releases/tag/v1.4.2).
Its owner-supplied Mozilla-approved XPI was anonymously downloaded over HTTPS and its SHA256 matched
`415e21433fa968a844fafccb4f393862523eb1d970222dcb88546314e5c5fb22` before activating metadata.
Do not add another installable version until its selected Mozilla-signed XPI release asset is published,
anonymously accessible over HTTPS, and matches the advertised SHA256.
Never advertise an unsigned XPI or source ZIP as an installable update. No native host, credentials,
browser profile, or AI-provider config belongs in this repository.

Install the Mozilla-signed 1.4.1 bootstrap normally in Firefox on the same profile, keeping the same
extension ID. Older versions without update_url need this one manual update. Avoid uninstalling solely
to update, as that may reset grants/preferences. Firefox's automatic-update settings still apply.
Already-installed signed 1.4.1 can discover 1.4.2 through the same endpoint; no repeat manual install
is required for that upgrade when automatic updates are enabled. Publication alone is not proof
that a particular Firefox installation has completed the upgrade.

Future selected signed assets use tag `vVERSION` and name `Luxios-Bridge-VERSION-signed.xpi` in this
repository's GitHub Releases. Metadata entry fields: `version`, `update_link` pointing to that exact
versioned release asset, and `update_hash` set to `sha256:` plus its actual lowercase 64-digit hash.
Do not silently replace versioned assets. Check ID/version/update_url and bounded safe package contents;
signature markers alone are not cryptographic proof. Firefox validates Mozilla's signature at install.

Publication does not prove that Firefox updated successfully. Test with an installed signed bootstrap
and a higher signed release before making that claim.

## 1.4.2 — 2026-10-13

### Fixed
- Ready paused/ended media observations skip the 400ms sample timer.
- Active progression can be verified after a 100ms sample, within the existing 400ms budget.
- Discovery and loading readiness share a bounded 2500ms read-only wait; loading is not inferred as
  autoplay rejection. Fresh refs, auth, ownership and permission guards remain unchanged.

Local verification: 118 tests passed. Browser timer throttling, YouTube loading and model latency
remain separate factors; no fixed end-to-end speed guarantee. The signed 1.4.1 release is retained.

## 1.4.1 — 2026-10-13

### Added
- Shortcuts for YouTube, Spotify, SIAM UB and GitHub; initial Firefox permission grants remain required.

### Changed
- Simpler popup and reusable, revocable site grants.
- Self-hosted update channel with a versioned signed asset and SHA256 integrity metadata.

### Fixed
- Publication version increased after the deleted 1.4.0 upload; site/media behavior is unchanged from 1.4.0.

Official guidance: [Updating your extension](https://extensionworkshop.com/documentation/manage/updating-your-extension/).
