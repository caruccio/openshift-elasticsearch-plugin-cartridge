OpenShift ElasticSearch Cartridge
=================================
Downloadable ElasticSearch cartridge for OpenShift.

To create your ElasticSearch app, run:

    rhc app create <your app name> http://cartreflect-claytondev.rhcloud.com/github/ncdc/openshift-elasticsearch-cartridge

If you want to create a ElasticSearch cluster, append the flag `--scaling`:

    rhc app create <your app name> http://cartreflect-claytondev.rhcloud.com/github/ncdc/openshift-elasticsearch-cartridge --scaling


Adding additional cluster nodes
===============================
To add more nodes to the cluster, simply add more gears:

    rhc cartridge scale -a <your app name> elasticsearch <number of total gears you want>


Plugins
=======
To install ElasticSearch plugins, edit the `plugins.txt` file, commit, and push your changes.

    cd elasticsearch
    vim plugins.txt
    git commit -a -m 'Incluindo plugin XXX'
    git push

You can also install plugins from a .zip file. Simply place it inside dir `plugins/`, git add, commit and push.

Configuration
=============

Configuration is build on-the-fly and starts with contents from file
config/elasticsearch.yml.erb, concatenated with any other file found in that
same dir (except for logging.yml and elasticsearch.in.sh). Files ending with
.erb will be pre-processed using ruby's erb command.


License
=======
This project is licensed under the [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).
