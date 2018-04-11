## scenario.json file
This file contains information on the scenario. And it is used during the creation of the virtual machine.

![scenario-json](../img/scenarios-json.png)

#### Description of scenario.json fields

* __name__: The name of the scenario
* __description__: Text to describe what the scenario contains
* __category__: Category of scenario
* __plugin-dependencies__: Description of the Vagrant plug-ins that are required to run the scenario
* __notes__: Any information you wish to advise the user on
* __version__: Version of the scenario
* __author__: Name of the Author
* __email__: Email address
* __disabled__: Currently not used
* __qlik-default-binary__: The Qlik software to use by default
* __resources__: URLs to present at the end of provisioning to enable users to connect
* __config__
    * __allowUpdates__: Currently not used
    * __Servers__
        * __name__: The name that will be the hostname of the server
        * __ip__: the IP address to assign the server
        * __box__: the name of the Vagrant box to use
        * __memory__: Amount of RAM to allocate
        * __cpus__: The number of cores to allocate
        * __sense__
            * __central__: if the server is a central node
            * __proxy__: Currently not used
            * __persistence__: Shared or Sync
