# NLexch Client for Elixir

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add nlexch_client to your list of dependencies in `mix.exs`:

        def deps do
          [{:nlexch_client, "~> 0.1.0"}]
        end

  2. Ensure nlexch_client is started before your application:

        def application do
          [applications: [:nlexch_client]]
        end

## Useage

More API document please visit [NLexch API](https://www.nlexch.com/documents/api-v2)

```
# Public API
NLexchClient.ticker market
NLexchClient.trades market

# Private API
# Create a API server with your key and secret.
NLexchClient.Server.start_link id, key, secret

# Get Member info
NLexchClient.me id

# Entry Order
NLexchClient.ask id, market, [{private, volume}, ...]
NLexchClient.bid id, market, [{private, volume}, ...]
NLexchClient.entry id, market, [{side, private, volume}, ...]

# Take Order info
NLexchClient.order id, order.id

# Cancel Order or all
NLexchClient.cancel_all id
NLexchClient.cancel_ask id
NLexchClient.cancel_bid id
