#gh:gh_sase-org__sase In the prompt input widget, if an xprompt is completed that doesn't have any
args or that has only one optional arg, we insert a space after the xprompt when the
user accepts the completion (e.g. hits `<enter>`). If the user is in the middle of a
sase snippet, this space is often manually deleted by the user before they press `<tab>`
again to travel to the next tabstop. Can you help me make it so this space is deleted
automatically in that case (when the user completes an xprompt and then immediately uses
`<tab>` to jump to the next snippet tabstop)? #plan