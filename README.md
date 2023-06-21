# ledger-cli-query
My ledger-cli queries.


## Filters

### Payee

Filter for 1 payee MERKUR
```
ledger reg -d "payee =~ /MERKUR/" 
```

Filter for 2 payees MERKUR OR SPAR
```
ledger reg -d "payee =~ /MERKUR|SPAR/" 
```

Payee MERKUR in account material.
```
ledger reg  @MERKUR material
```

### Amount

Transactions with amount equal 12.75 EUR.
```
ledger reg -d "amount == 12.75 EUR"
```

Amount between 50.00 EUR and 100.00 EUR.
```
ledger reg -d "amount < 100.00 EUR" and -d "amount > 50.00 EUR " -p jun
```

Amount between 50.00 EUR and 100.00 EUR and account
```
ledger reg -d "amount < 100.00 EUR" and -d "amount > 50.00 EUR " and -d "account =~ /hrana/" 
```

### Tag

Transactions with tag BONACA

- https://groups.google.com/g/ledger-cli/c/gyYCstT_twg/m/5lz44cmjAwAJ
- https://groups.google.com/g/ledger-cli/c/2hRFpqgHoIs/m/QRozJn2_AwAJ

```
ledger reg -l "has_tag('BONACA')"

OR

ledger reg  %BONACA
```

### Transfer between accounts.

Transaction from Transfer from A to B account.

- https://groups.google.com/g/ledger-cli/c/bkOsHgElPZk/m/bx_w8OQcAgAJ
- https://groups.google.com/g/ledger-cli/c/mgAsCkNJEU0/m/va4VsX9QAwAJ
- https://groups.google.com/g/ledger-cli/c/rXS0B1plkg4/m/l0huEfX0BQAJ

```
ledger bal sredstva:denar:A -l "any(account =~ /sredstva:denar:B/)"

OR 

ledger reg sredstva:denar:A -l "any(account =~ /sredstva:denar:B/)"
```

### Commodity

```
ledger bal  -l "commodity == 'HRK'"
```

### Capital Gains

- https://groups.google.com/g/ledger-cli/c/5De9q-QXxZM/m/PPd6WGAABAAJ

### Opening procedures

- https://groups.google.com/g/ledger-cli/c/u648SA1o-Ek/m/CVWCSK8LCgAJ

