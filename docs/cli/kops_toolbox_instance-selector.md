
<!--- This file is automatically generated by make gen-cli-docs; changes should be made in the go CLI command code (under cmd/kops) -->

## kops toolbox instance-selector

Generate instance-group specs by providing resource specs such as vcpus and memory.

### Synopsis

Generate AWS EC2 instance groups by providing resource specs, such as vcpus and memory, rather than instance types.

```
kops toolbox instance-selector INSTANCE_GROUP [flags]
```

### Examples

```
  ## Create a spot instance group using a MixInstancesPolicy and Capacity-Optimized spot allocation strategy.
  ## --flexible defaults to a 1:2 vcpus to memory ratio and 4 vcpus.
  kops toolbox instance-selector my-spot-mig --usage-class spot --flexible
  
  ## Create an on-demand instance group with custom vcpu and memory range filters.
  kops toolbox instance-selector ondemand-ig --vcpus-min=2 --vcpus-max=4 --memory-min 2gb --memory-max 4gb
```

### Options

```
      --allow-list string                 List of allowed instance types to select from w/ regex syntax (Example: m[3-5]\.*)
      --base-instance-type string         Base instance type to retrieve similarly specified instance types
      --burst-support                     Burstable instance types
      --cluster-autoscaler                Add auto-discovery tags for cluster-autoscaler to manage the instance-group (default true)
      --cpu-architecture string           CPU architecture [amd64, arm64] (default "amd64")
      --deny-list string                  List of instance types which should be excluded w/ regex syntax (Example: m[1-2]\.*)
      --dry-run                           Only print the object that would be created, without creating it. This flag can be used to create a cluster YAML or JSON manifest.
      --ena-support                       Instance types where ENA is supported or required
      --flexible                          Retrieve a group of instance types spanning multiple generations based on opinionated defaults and user overridden resource filters
      --gpu-memory string                 GPUs' total memory (Example: 4gb) (sets --gpu-memory-min and -max to the same value)
      --gpu-memory-max string             Maximum GPUs' total memory (Example: 4gb) If --gpu-memory-min is not specified, the lower bound will be 0
      --gpu-memory-min string             Minimum GPUs' total memory (Example: 4gb) If --gpu-memory-max is not specified, the upper bound will be infinity
      --gpus int                          Number of GPUs (Example: 4) (sets --gpus-min and -max to the same value)
      --gpus-max int                      Maximum Number of GPUs (Example: 4) If --gpus-min is not specified, the lower bound will be 0
      --gpus-min int                      Minimum Number of GPUs (Example: 4) If --gpus-max is not specified, the upper bound will be infinity
  -h, --help                              help for instance-selector
      --ig-count int                      Number of instance groups to create with different vcpus-to-memory ratios, starting at 1:2 and doubling
      --max-results int                   Maximum number of instance types to return back (default 20)
      --memory string                     Amount of memory available (Example: 4gb) (sets --memory-min and -max to the same value)
      --memory-max string                 Maximum Amount of memory available (Example: 4gb) If --memory-min is not specified, the lower bound will be 0
      --memory-min string                 Minimum Amount of memory available (Example: 4gb) If --memory-max is not specified, the upper bound will be infinity
      --network-interfaces int            Number of network interfaces (ENIs) that can be attached to the instance (sets --network-interfaces-min and -max to the same value)
      --network-interfaces-max int        Maximum Number of network interfaces (ENIs) that can be attached to the instance If --network-interfaces-min is not specified, the lower bound will be 0
      --network-interfaces-min int        Minimum Number of network interfaces (ENIs) that can be attached to the instance If --network-interfaces-max is not specified, the upper bound will be infinity
      --node-count-max int                Maximum number of nodes (default 10)
      --node-count-min int                Minimum number of nodes (default 1)
      --node-security-groups strings      Pre-created additional security groups for nodes
      --node-volume-size int              Instance volume size (in GiB) for nodes
  -o, --output string                     Output format. One of json or yaml. Used with the --dry-run flag. (default "yaml")
      --placement-group-strategy string   Placement group strategy: [cluster, partition, spread]
      --subnets strings                   Subnet(s) in which to create the instance group. One of Availability Zone like eu-west-1a or utility-eu-west-1a,
      --usage-class string                Usage class: [spot, on-demand] (default "on-demand")
      --vcpus int                         Number of vcpus available to the instance type (sets --vcpus-min and -max to the same value)
      --vcpus-max int                     Maximum Number of vcpus available to the instance type If --vcpus-min is not specified, the lower bound will be 0
      --vcpus-min int                     Minimum Number of vcpus available to the instance type If --vcpus-max is not specified, the upper bound will be infinity
      --vcpus-to-memory-ratio string      Ratio of vcpus to memory in MiB. (Example: 1:2)
```

### Options inherited from parent commands

```
      --add_dir_header                   If true, adds the file directory to the header of the log messages
      --alsologtostderr                  log to standard error as well as files (no effect when -logtostderr=true)
      --config string                    yaml config file (default is $HOME/.kops.yaml)
      --log_backtrace_at traceLocation   when logging hits line file:N, emit a stack trace (default :0)
      --log_dir string                   If non-empty, write log files in this directory (no effect when -logtostderr=true)
      --log_file string                  If non-empty, use this log file (no effect when -logtostderr=true)
      --log_file_max_size uint           Defines the maximum size a log file can grow to (no effect when -logtostderr=true). Unit is megabytes. If the value is 0, the maximum file size is unlimited. (default 1800)
      --logtostderr                      log to standard error instead of files (default true)
      --name string                      Name of cluster. Overrides KOPS_CLUSTER_NAME environment variable
      --one_output                       If true, only write logs to their native severity level (vs also writing to each lower severity level; no effect when -logtostderr=true)
      --skip_headers                     If true, avoid header prefixes in the log messages
      --skip_log_headers                 If true, avoid headers when opening log files (no effect when -logtostderr=true)
      --state string                     Location of state storage (kops 'config' file). Overrides KOPS_STATE_STORE environment variable
      --stderrthreshold severity         logs at or above this threshold go to stderr when writing to files and stderr (no effect when -logtostderr=true or -alsologtostderr=false) (default 2)
  -v, --v Level                          number for the log level verbosity
      --vmodule moduleSpec               comma-separated list of pattern=N settings for file-filtered logging
```

### SEE ALSO

* [kops toolbox](kops_toolbox.md)	 - Miscellaneous, infrequently used commands.

