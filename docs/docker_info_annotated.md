### ✅ **Raw Output**

```text
Client:
 Version:    28.3.2
 Context:    default
 Debug Mode: false
 Plugins:
  compose: Docker Compose (Docker Inc.)
    Version:  2.37.1
    Path:     /usr/lib/docker/cli-plugins/docker-compose

Server:
 Containers: 4
  Running: 2
  Paused: 0
  Stopped: 2
 Images: 39
 Server Version: 28.3.2
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Using metacopy: true
  Native Overlay Diff: false
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: systemd
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: c787fb98911740dd3ff2d0e45ce88cdf01410486.m
 runc version:
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.15.3-arch1-1
 Operating System: Arch Linux
 OSType: linux
 Architecture: x86_64
 CPUs: 16
 Total Memory: 15.35GiB
 Name: archlinux
 ID: 00a7fb44-96ba-4087-bbc3-afe926ddc28b
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Username: karimzakzouk
 Experimental: false
 Insecure Registries:
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false
```

---

### **Annotations (Key Insights)**

#### Client Section

* **Version**: `28.3.2` → CLI version installed.
* **Context**: `default` → Local Docker context.
* **Compose Plugin**: Installed at `/usr/lib/...`, version `2.37.1`.

#### Server Section (Docker Daemon)

* **Containers**: 4 total

  * 2 running, 2 stopped.
* **Images**: 39 local images.
* **Docker Version**: `28.3.2`.

#### Storage

* **Driver**: `overlay2` → Preferred for Linux; efficient for layer-based storage.
* **Backing FS**: `extfs` → Likely ext4, common Linux FS.
* **Supports d\_type / metacopy**: Storage optimizations.

#### Logging

* **Driver**: `json-file` (default) → Logs stored as JSON on host.

#### Cgroups

* **Driver**: `systemd`
* **Version**: 2 → Better control, unified resource hierarchy.

#### Plugins

* **Networks**: bridge, host, overlay, etc.
* **Volumes**: local
* **Logs**: Various supported log backends.

#### Security

* **seccomp**: Default syscall filter enabled.
* **cgroupns**: Isolated container view of cgroups.

#### Kernel & OS

* **Kernel**: `6.15.3-arch1-1`
* **OS**: Arch Linux
* **Arch**: x86\_64

#### Resources

* **CPUs**: 16
* **RAM**: 15.35 GiB

#### Docker Root

* **Directory**: `/var/lib/docker` → Where all container data lives.

#### User Info

* **Username**: karimzakzouk (Docker Hub)
* **Experimental Features**: Disabled
* **Live Restore**: Disabled (containers won’t stay up if Docker daemon crashes)
