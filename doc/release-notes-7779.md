Updated RPCs
------------

- `protx listdiff` now reports `platform_p2p` and `platform_https` in `addresses` for an EvoNode on legacy
  (pre-extended) addresses whenever a diff changes its core P2P address, pairing the new address with the
  node's current Platform ports as the full masternode state does. Previously they were reported only when the
  ports themselves changed, so without `-deprecatedrpc=service` a client could not learn the Platform ports of
  such an EvoNode if it first saw the node without an address and the node later got one with unchanged ports.
  Diffs that change only the ports still pair them with the placeholder address `255.255.255.255`, and the
  deprecated `platformP2PPort` / `platformHTTPPort` fields are unchanged. (#7779)
