#gh:gh_sase-org__sase I'm pretty sure the `toobig_split` chop is marking files as duplicates wrongly (see #sshot for context). We need to make sure that we only mark duplicates if the code base where the file lives (in this case "sase") has not changed at all (you can check the most recent git commit for that repo to accomplish this). Can you help me fix this?

#plan