# kubernetes-logstash-pipeline
Ready made code to parse logs from Kubernetes
**!!! Currently the Pipeline will works for kubernetes cluster which is runing with containerd as CRI.**

## Input and Output ##

This pipeline does not provide inputs or outputs so you can configure whatever you need. Files named `input.conf` and `output.conf` will not interfere with updates via git, so name your files accordingly.

Here are examples how your files could look if you want to use a local Redis instance.

```
input {
  redis {
    host => localhost
    key => "kubernetes"
    data_type => list
  }
}

output {
  redis {
    key => "forwarder"
    data_type => list
    host => localhost
  }
}
```
