# Gotchas — traps specific to this repo. Read before editing.

- ZeroMQ Port 5555 bind conflicts in `websocket_proxy/server.py#WebSocketProxy.__init__`: The proxy SUB socket binds `ZMQ_HOST:ZMQ_PORT` (port 5555). Running multiple OpenAlgo instances or rapid restarts without port release causes `ZMQError: Address in use`. Use `is_port_in_use` with a grace wait window.

Cite the code that proves each trap as `path#symbol` so [[conventions]] checks pass.
