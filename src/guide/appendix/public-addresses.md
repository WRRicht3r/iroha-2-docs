# Iroha public addresses

`TORII` the gatekeeper is the module in charge of handling in-coming and out-going connnections.
The `API_URL` is the location to which the client(s) make their requests. You can use it to change some peer-specific configuration options too. While we could give you the examples here, the only up-to-date description can be found in the Iroha’s immediate [documentation on GitHub](https://github.com/hyperledger/iroha/blob/iroha2-dev/docs/source/references/api_spec.md). Most of the time, the only reason to change the `API_URL` is to change the port, in case `8080` is either closed, or if you want to randomise ports to avoid certain kinds of attacks.
The `P2P_ADDR` is the internal address used for communication between peers. Take note of **this address** for inclusion in the `TRUSTED_PEERS` section of the configuration file.
Lastly, (and not in the example configuration) you have the prometheus endpoint address. It’s set by adding a value `"TELEMETRY_URL": "127.0.0.1:8180"`, to the `TORII` section. It’s not meant to be human-readable, but a `GET` request to the `127.0.0.1:8180/status` will give you a `json`-encoded representation of the top-level metrics, while a `GET` request to `127.0.0.1:8180/metrics` will give you a (somewhat verbose) list of all available metrics gathered in Iroha. You might want to change this, if you’re having trouble gathering metrics using `prometheus`.