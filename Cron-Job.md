# Cron Jobs

Cron jobs are user created scheduled jobs on a linux system to perform mundane task(s). They can be useful for important jobs like backing up a specific directory every day or to perform system updates every week on Thursday morning.

## Creating Cron Jobs

To create a Cron job running as a user just type in the following:
```bash
crontab -e
```
#### Note: It may ask you what editor you want to use, for most people nano is fine.

To run a cron job as root (can be dangerious if not careful) do the same command running as sudo or logon as root in the terminal.
```bash
sudo crontab -e
```

## Cron Job Formats

When you create a cron job for the first time the crontab file will be blank except for the default notes, the cron tab will be in the format of 5 numeric values follow by a command or a script. You also must me mindful of the system time that you are making the scripts on.

Example:
```
* * * * * /path/to/script.sh
```
Cron will ceck every minute to see if it needs to run a cron job, the table below is the format of how times are specified:
```
|------------Minute (Valid Values: 0-59)
| |----------Hour (Valid Values: 0-23, 0=Midnight)
| | |--------Day of Month (Valid Values: 1-31)
| | | |------Month (Valid Values: 1-12)
| | | | |----Day of Week (Valid Values: 0-6, 0=Sunday)
* * * * * /path/to/script.sh
```

## Time Examples

### To run a script every minute indefinitely:
```
* * * * * /path/to/script-or-command
```

### To run a script every 10 minutes:
```
*/10 * * * * /path/to/script-or-command
```
or another equivelant but valid syntax:
```
0,10,20,30,40,50 * * * * /path/to/script-or-command
```
### To run a script every Wednesday at 3AM
```
0 3 * * 3 /path/to/script-or-command
```
### To run a command on 01 and 31 past the hours of 4:00am and 5:00am on the 1st through the 15th of every January and June.
```
01,31 04,05 1-15 1,6 * /path/to/script-or-command
```

## More Friendly Timers

Cron also offers more friendly timers to start scripts if the table above is confusing.

|Friendly Version|Uses|
|---|---|
|@reboot| Starts a script at reboot/boot|
|@yearly| Runs once a year (Same as 0 0 1 1 * )|
|@annually| same as @yearly|
|@monthly| Run once a month (Same as 0 0 1 * * )|
|@weekly| Run once a week (Same as 0 0 * * 0 )|
|@daily| Run once a day (Same as 0 0 * * * )|
|@midnight| Same as @daily|
|@Hourly| Run once an hour (Same as 0 * * * * )|

Examples:
```
@reboot /path/to/script-or-command
```
