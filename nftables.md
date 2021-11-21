# Simple commands

## Tables
List tables
```bash
nft list tables
```
List rules in table
```
nft list table inet inet-table
```

Add, remove and flush example `inet-table`:
```bash
nft add table inet inet-table
nft delete table inet inet-table
nft flush table inet inet-table
```

## Chains
```bash
nft add chain inet inet-table my_chain '{type filter hook input priority 0; }'
```

```
nft add chain inet inet-table input-filter-chain
nft delete chain inet inet-table input-filter-chain
nft flush chain inet inet-table input-filter-chain
```

## Rules

```
nft add rule inet inet-table input-filter-chain tcp dport 22 counter accept
```

```
nft add rule inet inet-table input-filter-chain ip daddr 1.1.1.1 counter
```
