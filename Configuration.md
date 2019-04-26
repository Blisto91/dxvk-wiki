Some applications may require quirks in order to run or improve performance. While DXVK enables some of them by default if necessary, they can be overridden by using a configuration file.

**Note that overriding the default options is usually not necessary and may cause issues!**

## Configuration file
By default, DXVK will try to load `dxvk.conf` from the current working directory, i.e. the directory where the log files will be created. This is usually the same directory where the game exe is located.

In order to change the configuration file path, set the environment variable `DXVK_CONFIG_FILE`, e.g.:
```
DXVK_CONFIG_FILE=/home/xxx/dxvk.conf
```

## Example configuration
The [configuration file](https://github.com/doitsujin/dxvk/blob/master/dxvk.conf) in the repository documents all the options that are currently available, and leaves them to their default values. Uncomment an option by removing the `#` in order to override it.

## Per-app configuration
One or more configuration options can be restricted to a single application as follows:
```
[app.exe]
dxvk.option = value
```
This overrides the given option for `app.exe`, other applications remain unaffected. The name matching will work even if the exe name contains a `[` or `]` character itself, wildcards however are not and will not be supported.

**Note:** This feature is not yet available in version 1.0.3.