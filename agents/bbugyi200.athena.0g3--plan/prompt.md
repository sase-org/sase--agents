#gh:gh_sase-org__sase When a gate option is selected, it is the gate shell node's status that should
be updated, NOT the node of the agent shell corresponding with the sase agent that
created the gate. For example, in #sshot, the `0g0.w0--gate` gate shell should have the
`TALE APPROVED` status, not the `0g0.w0--plan` agent shell (this should have the other
desirable effect of causing the `0g0.w0` agent family node to have a status of
`TALE APPROVED` as well, since agent family nodes should have the same status as their
most recently run shell). Can you help me fix this?

#plan #m_opus