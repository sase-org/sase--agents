#gh:gh_sase-org__sase Can you help me make the `wait_checks` chop much faster without changing its
behavior in any way? The goal is to make this chop work consistently even on machines
with low resources or machines with high load (which happens a lot on this machine when
there are a lot of sase agents running, for example).

#plan %m:claude-fable-5 %w(runners=3)