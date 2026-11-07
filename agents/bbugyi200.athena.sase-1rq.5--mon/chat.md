# Chat History - ace-run (sase-1rq.5--mon)

- **TIMESTAMP:** 2026-11-07 09:35:30 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1rq.5--mon

## Prompt

sase monitor start --command 'set -eu\nrepo=bbugyi200/dotfiles\nsubject="fix(tests): use grep instead of rg in doctl_login_test"\nstart=$(date +%s)\nwhile :; do\n  runs=$(gh run list -R "$repo" -b master -w CI -e push --json databaseId,headSha,displayTitle,event,attempt,status,conclusion,createdAt)\n  run_id=$(printf "%s" "$runs" | jq -r --arg subject "$subject" ".[] | select(.displayTitle == \\\\\\"$subject\\\\\\") | .databaseId" | head -n 1)\n  if [ -z "$run_id" ]; then\n    run_id=$(printf "%s" "$runs" | jq -r ".[] | select(.event == \\\\\\"push\\\\\\" and (.headSha | startswith(\\\\\\"e9316957\\\\\\") | not)) | .databaseId" | head -n 1)\n  fi\n  if [ -n "$run_id" ]; then break; fi\n  now=$(date +%s)\n  if [ "$((now - start))" -ge 5400 ]; then\n    printf "TIMEOUT: no push CI run for the landed fix appeared within 90 minutes.\\n"\n    exit 1\n  fi\n  sleep 60\ndone\ngh run watch "$run_id" -R "$repo" --exit-status\ngh run list -R "$repo" -b master -w CI -L 5 --json databaseId,headSha,displayTitle,event,attempt,status,conclusion,createdAt,updatedAt' --reason 'Watch bbugyi200/dotfiles CI after the approved doctl test portability fix lands'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.displayTitle == \"fix(tests): use grep instead of rg in doctl_login_test\") | .databaseId                              
jq: 1 compile error
jq: error: syntax error, unexpected INVALID_CHARACTER (Unix shell quoting issues?) at <top-level>, line 1:
.[] | select(.event == \"push\" and (.headSha | startswith(\"e9316957\") | not)) | .databaseId                       
jq: 1 compile error
TIMEOUT: no push CI run for the landed fix appeared within 90 minutes.

