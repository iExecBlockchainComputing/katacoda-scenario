# Buy & Run work using Marketplace

let's init work order fields in `iexec.json`:

`iexec order init --buy`{{execute}}

Let's edit `iexec.json` and customize the buy order fields. Particularly work params field.

`vi iexec.json`{{execute}}

Let's show marketplace orderbook and pick an order ID

`iexec orderbook show --category 5`{{execute}}

Pick an order ID from previous result, and let's trigger our work by filling the order:

`iexec order fill <orderID>`{{execute}}

let's watch progress of the submitted work, and download its result when completed:

`iexec work show --watch --download`{{execute}}

Congrats! You just bought a work execution at the best price from the iExec Marketplace, and downloaded the result.

# Don't waste money!

Before closing your browser window, be nice and give back your RLC and ETH to iExec Faucet by sweeping your wallet:

`iexec wallet sweep --to 0xc3fb2431042fbdde67b8356abcabbc5c14660849`{{execute}}

Thank you!
