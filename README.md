# *M. tuberculosis* phylogeny IRIDA plugin

![tb-phylogeny-pipeline-plugin](https://github.com/COMBAT-TB/irida-plugin-tb-phylogeny/workflows/tb-phylogeny-pipeline-plugin/badge.svg)

This project contains a M tuberculosis phylogeny pipeline implemented as a plugin for the [IRIDA](https://irida.ca) bioinformatics analysis system.

## Using the IRIDA Builder Docker container

To build using Docker and the IRIDA Builder Docker container, run:

```bash
mkdir output
build/build_workflow.sh . output
```

The JAR file for the compiled pipeline will be in the `output` directory.

## Building/Packaging

Building and packaging this code is accomplished using [Apache Maven][maven]. However, you will first need to install [IRIDA](https://github.com/phac-nml/irida) to your local Maven repository.

## Installing IRIDA to local Maven repository

To install IRIDA to your local Maven repository please do the following:

Clone and install the IRIDA project to local repository

```bash
git clone https://github.com/phac-nml/irida.git
cd irida
mvn clean install -DskipTests
```

## Building the plugin

Once you've installed IRIDA as a dependency, you can proceed to building this plugin. Please run the following commands:

```bash
git clone https://github.com/COMBAT-TB/irida-pipeline-plugins.git
cd irida-pipeline-plugins/snippy-pipeline-plugin
mvn clean package
```

Once complete, you should end up with a file `target/snippy-pipeline-plugin-0.1.1-SNAPSHOT.jar` which can be installed as a plugin to IRIDA.

If you have previously [setup IRIDA][irida-setup] before you may copy this JAR file to `/etc/irida/plugins` and restart IRIDA. The plugin should now show up in the **Analyses > Pipelines** section of IRIDA.

## Dependencies

The following dependencies are required in order to make use of this plugin.

- [IRIDA][] >= 19.01.1
- [Java][] >= 1.8 and [Maven][maven] (for building)

[maven]: https://maven.apache.org/
[irida]: http://irida.ca/
[galaxy]: https://galaxyproject.org/
[java]: https://www.java.com/
[irida-setup]: https://irida.corefacility.ca/documentation/administrator/index.html
