## Curve Finance Subgraph

## Links

- Protocol Website: https://curve.fi
- Protocol documentation: https://curve.readthedocs.io
- Smart contracts: https://github.com/curvefi/curve-contract
- Deployed Addresses: https://curve.readthedocs.io/ref-addresses.html
  "# Curve Subgraph"

=======================================================
Core Notetaking on the Curve Platform:

There are 3 types of pools you need to be aware of:

    1. Plain Pools [Any comp of stable assets paired with together with another stable asset]
    2.Lending Pools [Where symbolic representations
      of certain assets are pooled together]
    3. Metapools [where a stablecoin can be paired
      with an LP [Liquidity Provider] token of another pool]

Then there are LP Tokens, which are what is given to Liquidity Providers,
and this in the case of CURVE is the CRV token, which has gov'nce capabilities,
or be deposited into a metapool to be paired with a stablecoin.

=======================================================

## If we can index the StableSwap pieces alone that'd be massive win, so let's just

# Try to break those down and get to it.

So I think we have Just enough understanding of some of the core contracts to try
to look at the abi's and see what's there

==========================================================
Events from each contract:

The Pool Events:

Event #1: TokenExchange(address provider, uint256[3] token_amounts , uint256[3] fees, uint256[3] invariant, uint256 token_supply)

Event #2: AddLiquidity(address provider, uint256[3] token_amounts , uint256[3] fees, uint256 token_supply)

Event #3: RemoveLiquidity(address provider, uint256[3] token_amount, uint256[3] coin_amount)

Event #4: RemoveLiquidityOne(address provider, uint256[3] token_amounts, uint256[3] fees, uint256 invariant, uint256 token_supply)

Event #5: RemoveLiquidityImbalance(uint256 deadline, admin address)

Event #6: commitNewAdmin(address admin)

Event #7: commitNewFee(uint256 fee, uint256 admin_fee)

Event #8: NewFee(uint256 old_A, uint256 new_A, uint256 initial_time, uint256 future_time)

Event #9: RampA(A uint256, uint256 t)

Event #10: StopRampA(address \_owner, address[3] \_coins, address \_pool_token, uint256 \_A, uint256 \_fee, uint256 \_admin_fee)

==========================================================

Token Events:

Event #1: Transfer(address \_owner, address \_spender, uint256 \_value)

Event #2: Approval(string \_name, string \_symbo, uint256 \_decimals, uint256 \_supply,)

==========================================================

Ok we got the vents now it's time to understand how these events
play into one another.

What's the best strategy to do that? well let's start with explaining the context in which each event is set off, if we know that we're then able to understand the what actions set off what events, which is a half-step to where we want it to be.

Let's eat breakfast then do that... this feels good let's keep progressing. when we do that let's try to make a graph of how we plan on architecting it send that to amrit, and ask him how that's done.
"# curve-subgraph" 
