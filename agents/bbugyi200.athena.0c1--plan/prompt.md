#gh:gh_sase-org__sase Yesterday, we fixed the `toobig_split` chop's duplicate handling by checking the HEAD commit. This was a hacky, bad solution. Can you help me get rid of this solution in favor of using the new `%if` directive for this (see the sase-s6 epic bead for context)? This directive should accept a code block that ensures that the file is still >=700 lines long.

#plan