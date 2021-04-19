# MySQL

- Flow of statements
    - https://dev.mysql.com/doc/internals/en/guided-tour-flow.html
    - The flow works like this:
        - First, the client routines get an SQL statement from a user, allowing edit, performing initial checks, and so on.
        - Then, via the vio routines, the somewhat-massaged statement goes off to the server.
        - Next, the sql routines handle the parsing and call what's necessary for each individual part of the statement. Along the way, the sql routines will be calling the low level mysys routines frequently.
        - Finally, one of the ha (handler) programs in the sql directory will dispatch to an appropriate handler for storage. In this case we've assumed, as before, that the handler is myisam — so a myisam-directory program is involved. Specifically, that program is mi_write.c, as we mentioned earlier.
- 2PC: Two phase commit
    + https://shekhargulati.com/2018/09/05/two-phase-commit-protocol/
        * In the Two-phase commit protocol, there are two phases (that’s the reason it is called Two-phase commit protocol) involved. The first phase is called prepare. In this phase, a coordinator (either a separate node or the node initiating the transaction) makes a request to all the participating nodes, asking them whether they are able to commit the transaction. They either return yes or no in the response. They return yes if they can successfully commit the transaction or no if they unable to do so.
        * In the second phase, coordinator decides based on the votes whether to send the commit or abort request to the participating nodes. This phase is called the commit phase.
        * If all the participating nodes said yes, then commit request is sent to all the node.
        * If any of the participating nodes said no, then abort request is sent to all the nodes

