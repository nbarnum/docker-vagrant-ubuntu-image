Ubuntu 16.04 (xenial) Docker image for use with Vagrant Docker provider.

## Use with Vagrant

You must have [Vagrant](https://www.vagrantup.com/) and [Docker](https://docs.docker.com/install/) installed to use this image.

### Minimal Vagrantfile

```
Vagrant.configure('2') do |config|
  config.ssh.username = 'root'

  config.vm.provider :docker do |d|
    d.image = 'nbarnum/vagrant-ubuntu'
    d.has_ssh = true
  end
end
```

See [Vagrant docs](https://www.vagrantup.com/docs/docker/) for additional information on Docker provider.

Create the container with Vagrant:

```
$ vagrant up
Bringing machine 'default' up with 'docker' provider...
==> default: Creating the container...
<snip...>
==> default: Machine booted and ready!
```

SSH into the container:

```
$ vagrant ssh
Welcome to Ubuntu 16.04.4 LTS (GNU/Linux 4.9.60-linuxkit-aufs x86_64)
root@5cf0747b3d40:~#
```
