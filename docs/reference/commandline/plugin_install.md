# plugin install

<!---MARKER_GEN_START-->
Install a plugin

### Options

| Name                      | Type     | Default | Description                                       |
|:--------------------------|:---------|:--------|:--------------------------------------------------|
| `--alias`                 | `string` |         | Local name for plugin                             |
| `--disable`               |          |         | Do not enable the plugin on install               |
| `--disable-content-trust` |          |         | Skip image verification                           |
| `--grant-all-permissions` |          |         | Grant all permissions necessary to run the plugin |


<!---MARKER_GEN_END-->

## Description

Installs and enables a plugin. Docker looks first for the plugin on your Docker
host. If the plugin does not exist locally, then the plugin is pulled from
the registry. Note that the minimum required registry version to distribute
plugins is 2.3.0.

## Examples

The following example installs `vieus/sshfs` plugin and [sets](plugin_set.md) its
`DEBUG` environment variable to `1`. To install, `pull` the plugin from Docker
Hub and prompt the user to accept the list of privileges that the plugin needs,
set the plugin's parameters and enable the plugin.

```console
$ docker plugin install vieux/sshfs DEBUG=1

Plugin "vieux/sshfs" is requesting the following privileges:
 - network: [host]
 - device: [/dev/fuse]
 - capabilities: [CAP_SYS_ADMIN]
Do you grant the above permissions? [y/N] y
vieux/sshfs
```

After the plugin is installed, it appears in the list of plugins:

```console
$ docker plugin ls

ID             NAME                  DESCRIPTION                ENABLED
69553ca1d123   vieux/sshfs:latest    sshFS plugin for Docker    true
```

## Related commands

* [plugin create](plugin_create.md)
* [plugin disable](plugin_disable.md)
* [plugin enable](plugin_enable.md)
* [plugin inspect](plugin_inspect.md)
* [plugin ls](plugin_ls.md)
* [plugin push](plugin_push.md)
* [plugin rm](plugin_rm.md)
* [plugin set](plugin_set.md)
* [plugin upgrade](plugin_upgrade.md)
