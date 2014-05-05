# ELK

### Elasticsearch, Logstash, Kibana

---

![ELK](http://www.montaneelk.com/images/elk_gallery_12.jpg)

---

# Elasticsearch

---

### Schema-free, replicated and sharded data storage

REST + JSON interface

Note:
Elasticsearch is a schema-free storage which means that its not bound to any
type of schema. Its also replicated so that you can set that any index can
exist on more than one node. Sharded data means that you can split your data
into multiple small parts and distribute them on several nodes. Different
parts can be replicated on different nodes.
Protip: Give ES enough memory.

---

# Logstash

---

### Collect, parse and store log data

Note:
Logstash is used to collect logs from servers, either via Syslog or a separate
log agent. It can then be parsed in Logstash to separate fields, add tags,
increment counters, send data to systems that collect metrics or alert on
them. The structured data can then be indexed and stored by the various
outputs provided. One of those are Elasticsearch.

---

# Kibana

---

### Visualize logs stored in Elasticsearch

Note:
Kibana can be used to visualize the logs stored in ES. Kibana provides a nice
interface and easy access to the mountains of logs. Elasticsearch makes it
fast to search through the logs and in that way makes the work of finding
errors or weird access patterns in terabytes of log data.

---

![Kibana
UI](http://www.elasticsearch.org/content/uploads/2013/08/Screen-Shot-2013-07-11-at-5.00.28-PM.png)

---

### Logs, keep and use them!

They will tell you a lot about your customers and your application

Note:
Logs are an important part of any application. In order to keep track of users
and errors in the application its important to look through logs in an
organized way. Reading line for line when 500 users are clicking through your
website is not an option. In our case we are also keeping logs for security
audits and looking at different email patterns.

---

![Logs Workflow](http://rashidkpc.github.io/Kibana/images/metrics.png)

---

# FIN

---

Images:

* [Sinclair Imagery Inc.](http://www.montaneelk.com/updates_elk.php)
* [Elasticsearch](http://elasticsearch.org), Elasticsearch BV.

---

Recommended reading:

* http://elasticsearch.org
* http://logstash.net
