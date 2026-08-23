#gh:sase-org/sase
%id(split_file.src.sase.main.parser_agent.0, clan=toobig-3m)
%model:@medium
%wait:toobig-3m.split_file.src.sase.ace.tui.widgets._agent_list_render_agent.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/main/parser_agent.py