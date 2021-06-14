# FILE BACKUP SCRIPT

this project purpose is how to backup file or directory to `.tar.gz` file, so in this case the basic requirement is `tar` package, the next purpose is script can remote backup with `ssh-exec` and remote backup files

> #### option
- [x] basic backup with `retain days`
- [ ] merge all file in month to single file with `retain years/month` *optional
- [ ] remote backup
- [ ] integrate with `dbbackup-manager`

### How to deploy
in this case of backup system, we need `cronjob` you can run manually the script using this commmand line
```bash
  $ ./code-backup [apps-name] [source-to-backup] [target-to-backup]
```
the default cron-job event will setting one backup period everyday, and will delete the early one at last 30 retain days, script like bellow
```bash
0 0 */1 * * /path/to/code-backup sample-apps /path/to/sample-apps /path/to/target
```

> don't be hesitate to make `issue` or `pull-request` :>