# Puppet

### An introduction to configuration management

---

## Configuration management

> "Configuration management (CM) is a systems engineering process for
> establishing and maintaining consistency of a product's performance,
> functional and physical attributes with its requirements, design and
> operational information throughout its life"
[Wikipedia](http://en.wikipedia.org/wiki/Configuration_management)

Note:
When designing a system that contains multiple nodes, we need to keep some
configuration files the same and have them perform consistent. That is why we
use a CM. We can use a framework for keeping files, packages and settings in
sync.

---

## Alternatives

CFEngine, Chef, Ansible, Salt..

Note:
There are many alternatives to Puppet. At our company we are using Puppet and
that is why we focus on it now.

---

## Server/Client Architecture

Standalone possible

Note:
Puppet runs as a daemon and communicates with a master. However it is also
possible to run it standalone.

---

## Asset management

Note:
Puppet can in a way be used as asset management with something called facts.
Facts can then be used to do either change behavior of the node or to query in
reports. For example, we have a script that queries the data collected by
Puppet to draw a map of all our nodes.

---

## Facter

  ```
  root@ermahgerd:~# facter
  architecture => amd64
  domain => example.com
  facterversion => 1.6.10
  fqdn => ermahgerd.example.com
  hardwareisa => x86_64
  ipaddress_eth0 => 192.168.11.80
  ipaddress_lo => 127.0.0.1
  is_virtual => false
  ```

Note:
Enter facter, the system that collects facts.

---

![Foreman screenshot](http://projects.theforeman.org/attachments/download/319/dashboard.png)

---

## Puppet DSL

  ```ruby
  package { 'apache2':
    ensure => present,
  }
  ```

  ```ruby
  file { '/etc/motd':
  ensure => present,
  content => "Hello World\n",
  owner => root,
  group => root,
  }
  ```

  ```ruby
  user { 'anton':
  ensure => present,
  }
  ```

  Note:
  Puppet has an own Domain Specific Language, it is built to be
  simple for sysadmins to use and the biggest caveats is that it is
  declarative and resources can run in any order unless declared
  otherwise. Package is the same syntax no matter which platform you
  are running.

---

### The catalog: compiled resources

Note:
Puppet compiles the manifests you write to something called a catalog. This is
used on the end nodes and stores the relationships of the resources that are
going to be run.

---

## Reports

Can be used by for example Foreman

Note:
Puppet can send reports of runs to an API endpoint.

---

![Puppet dataflow](http://aosabook.org/images/puppet/dataflow.png)

---

## Modules

Examples: apache2, mysql, powerdns

Note:
Modules are reusable parts of Puppet code that can be used by multiple
organizations with a some changes. There may already be a module for
automation of apache2, mysql, powerdns and so on.

---

## Self documenting, repeatable, automated

---

Recommended reading:
* http://puppetlabs.com
* http://docs.puppetlabs.com
* [Pro Puppet](https://www.apress.com/9781430230571)
* [In Search of
  Certainty](http://www.amazon.com/In-Search-Certainty-Information-Infrastructure-ebook/dp/B00ENEEWYO)
