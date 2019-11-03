Bitcoin Core version 0.12.1 is now available from:

Notable changes
===============
=================

Detailed release notes follow. This overview includes changes that affect
behavior, not code moves, refactors and string updates. For convenience in locating
the code changes and accompanying discussion, both the pull request and
git merge commit are mentioned.

### RPC and REST

Asm script outputs now contain OP_CHECKLOCKTIMEVERIFY in place of OP_NOP2
-------------------------------------------------------------------------

OP_NOP2 has been renamed to OP_CHECKLOCKTIMEVERIFY by [BIP
65](https://github.com/bitcoin/bips/blob/master/bip-0065.mediawiki)

The following outputs are affected by this change:
- RPC `getrawtransaction` (in verbose mode)
- RPC `decoderawtransaction`
- RPC `decodescript`
- REST `/rest/tx/` (JSON format)
- REST `/rest/block/` (JSON format when including extended tx details)
- `bitcoin-tx -json`

### Configuration and command-line options

### Block and transaction handling
- #7543 `834aaef` Backport BIP9, BIP68 and BIP112 with softfork (btcdrak)

### P2P protocol and network code
- #7804 `90f1d24` Track block download times per individual block (sipa)
- #7832 `4c3a00d` Reduce block timeout to 10 minutes (laanwj)

### Validation
- #7821 `4226aac` init: allow shutdown during 'Activating best chain...' (laanwj)
- #7835 `46898e7` Version 2 transactions remain non-standard until CSV activates (sdaftuar)

### Build system
- #7487 `00d57b4` Workaround Travis-side CI issues (luke-jr)
- #7606 `a10da9a` No need to set -L and --location for curl (MarcoFalke)
- #7614 `ca8f160` Add curl to packages (now needed for depends) (luke-jr)
- #7776 `a784675` Remove unnecessary executables from gitian release (laanwj)

### Wallet
- #7715 `19866c1` Fix calculation of balances and available coins. (morcos)

### Miscellaneous
- #7617 `f04f4fd` Fix markdown syntax and line terminate LogPrint (MarcoFalke)
- #7747 `4d035bc` added depends cross compile info (accraze)
- #7741 `a0cea89` Mark p2p alert system as deprecated (btcdrak)
- #7780 `c5f94f6` Disable bad-chain alert (btcdrak)

Credits
=======

Thanks to everyone who directly contributed to this release:

- accraze
- Alex Morcos
- BtcDrak
- Jonas Schnelli
- Luke Dashjr
- MarcoFalke
- Mark Friedenbach
- NicolasDorier
- Pieter Wuille
- Suhas Daftuar
- Wladimir J. van der Laan

As well as everyone that helped translating on [Transifex](https://www.transifex.com/projects/p/bitcoin/).
