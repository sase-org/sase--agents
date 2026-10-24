#gh:gh_sase-org__sase I would like to start instructing agents to start using `weight=0` for the
`%queue` directive when using a /sase_monitor to wait for some event (see the nodes with
the `WATCHING MASTER GATE` and `WAITING FOR CORE` statuses in the
~/tmp/screenshots/20261024_135951.png screenshot for an example of monitors that should
have a weight of 0), but I'm not sure how to do this? Can you do some research with the
goal of helping me decide which macros need updating? End your analysis with a set of
recommended changes. #research(diagrams=true) %q(1.5x,w=0.25) %m:@xlarge