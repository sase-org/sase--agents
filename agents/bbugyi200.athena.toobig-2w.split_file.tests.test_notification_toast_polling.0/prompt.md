#gh:sase-org/sase
%id(split_file.tests.test_notification_toast_polling.0, clan=toobig-2w)
%wait:toobig-2w.split_file.tests.test_bead.test_sync.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_notification_toast_polling.py