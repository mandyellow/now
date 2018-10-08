# INSTALL

`now` script will be *deprecated* soon and the installation with the purpose of test Tsuru and/or for development, you can use [installer](https://docs.tsuru.io/master/experimental/installer.html) to have Tsuru up and running. Installer is an experimental feature.

<br/>

# Tsuru Now

Yet another script to install Tsuru and its dependencies on Ubuntu or Debian distros.

These are some goals for this project:

* It should run without interaction and deliver a working environment.
* It shouldn't be a problem to run the script multiple times on the same machine.
* It should work on existing machines that might already have some components installed.
* It should allow parameters to install a single role:
    * API node;
    * Docker node;
    * Load balancer node.
* A web UI to automatically run it on EC2 instances.

*Note: This scripts works only on Debian or Ubuntu distros, isn't supported to run on CentOS/RHEL.*

## Running

Running the command below should already create a working Tsuru environment:

```
curl -sL https://raw.githubusercontent.com/tsuru/now/master/run.bash | bash
```

<br/>

## Advanced Usage

With Tsuru Now, you can build your own Tsuru cluster easily.

### Building a cluster server

```
curl -sL https://raw.githubusercontent.com/tsuru/now/master/run.bash | bash -s -- --template server
```


### Building a client connected to the server

Assume the IP address of the cluster server is 10.42.42.1

```
curl -sL https://raw.githubusercontent.com/tsuru/now/master/run.bash | bash -s -- --template client --private-ip 10.42.42.1
```


### Building a docker node controlled by the server

Assume the IP address of the cluster server is 10.42.42.1

```
curl -sL https://raw.githubusercontent.com/tsuru/now/master/run.bash | bash -s -- --template dockerfarm --private-ip 10.42.42.1
```
