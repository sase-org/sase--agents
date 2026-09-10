#gh:gh_sase-org__sase #fork:0ix Also when we disabled the Grok provider automatically after this
event, we automatically used a disablement time of 2 days. I'm guessing this is because
the error message did not specify how much time was left until the usage limit was
reset; however, we recently implemented LLM provider usage collectors, which also have
access to the date and time of the usage windows. Can you help me start falling back to
use the usage collector data to determine the disablement time in the future?

#plan %m:@xlarge