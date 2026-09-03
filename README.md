# Plockaröversikt WebApp releases

Public, signed release artifacts for the local Plockaröversikt WebApp. The
download contains the application only: no ASK operational data, local
configuration, or source exports are included.

## Install on Windows

1. Download
   [`Install-Plockaroversikt-WebApp.bat`](https://github.com/AnakinThighwalker/Plockaroversikt-WebApp-Releases/releases/latest/download/Install-Plockaroversikt-WebApp.bat).
2. Double-click the BAT as the ordinary Windows user. Do not run it as
   administrator.
3. The first setup downloads its own runtimes and packages, creates
   `Plockaroversikt.bat` on the Desktop, and opens
   `http://127.0.0.1:3010` in the default browser.
4. Import that PC's ASK exports locally through ASK Pulse.

The first import needs Plocklogg Full, Pallastning, Item Alias, and the export
from the actual ASK tab **Statuslogg Kundorder**. Exact compatible names include
`plocklogg`, `Plocklogg Full`, or `v_ask_pick_log_full`; `pallastning`,
`Pallastningslogg`, or `v_ask_palletloading_log`; `Item Alias`, `Item_Alias`,
`ItemAlias`, `Artikel Alias`, or `ArtikelAlias`; and `Statuslogg Kundorder`,
`v_ask_statuslog_customer_order`, `Orderstatus`, `Order Status`, or legacy
`till Antonio`. Append `.csv`. Optional movements accept `v_ask_trans_log`,
`Translogg`, `Transaktionslogg`, `Förflyttningslogg`, or
`Forflyttningslogg`. No renaming is required when an export already uses one
of these names. If the first import cannot run, ASK Pulse names the required
exports that are missing or unusable. After the baseline exists, ordinary
picker updates need only a new Plocklogg Full export.

Every name is case-insensitive and supports a 14-digit ASK export timestamp,
the normal Windows `(N)` duplicate suffix, or both. If several completed copies
exist, the newest validated file is imported and older copies are left
untouched. Similar or partial names are rejected, and every recognized file
must still pass its complete feed-specific header validation.

The first setup needs internet access and 64-bit Windows 10/11 or Windows
Server 2016+. It does not require Git, a GitHub account, Node.js, Python, or
administrator rights. An organization can still block BAT or PowerShell files
through AppLocker or another administrator policy.

## Updates and integrity

Settings checks the public release manifest manually. Immutable releases are
enabled on this artifact repository. Every package is bound
to its size and SHA-256 digest and the manifest is verified with the public key
embedded in the installer. Signature verification is not bypassed.

See the [latest release](https://github.com/AnakinThighwalker/Plockaroversikt-WebApp-Releases/releases/latest)
for the installer, signed manifest, package, and exact file inventory.
