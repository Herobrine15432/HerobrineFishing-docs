# Installation

## Requirements

- Paper 26.2 stable
- Java 25
- Optional WorldGuard 7.0.18
- Optional Vault and an economy provider

1. Stop the server.
2. Place the current HerobrineFishing JAR in `plugins/`.
3. If replacing an incompatible earlier implementation, rename or archive its old data folder and allow this version to create a clean `plugins/HerobrineFishing/` folder.
4. Start the server and confirm the enable log reports 80 fish, 8 rods, and 8 baits.
5. Add WorldGuard and/or Vault only if their documented features are wanted.

Do not install ProtocolLib or an NMS compatibility layer; neither is used. Never copy a database or YAML set from a rejected architecture into production without staging validation.
