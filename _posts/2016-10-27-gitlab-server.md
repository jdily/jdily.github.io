---
layout: post
title: GitLab configuration and running.
---

I set up a gitlab server on my ubuntu server, here is the path and relevant commands.

### basic setting

* config file : /etc/gitlab/gitlab.rb

  * set url : **external_url**
  * back up path : **backup_path**

after configuring, run

```
sudo gitlab-ctl reconfigure
```

```
sudo gitlab-ctl restart
```

### back up
```
sudo gitlab-rake gitlab:backup:create
```

I also schedule a daily backup for everyday by

```
0 2 * * * /opt/gitlab/bin/gitlab-rake gitlab:backup:create CRON=1
```
---

## TODO

* set the sync between backup files to my dropbox.
