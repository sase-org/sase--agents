%wait(sase-ab.1, sase-ab.2, sase-ab.3, sase-ab.5, priority=15)
%wait(bead=sase-ab.1)
%wait(bead=sase-ab.2)
%wait(bead=sase-ab.3)
%wait(bead=sase-ab.4)
%wait(bead=sase-ab.5)
#gh:gh_sase-org__sase
%id(land, clan=sase-ab, bead=sase-ab)
%model:@big_epic_lander
%auto
#bd/land_epic:sase-ab