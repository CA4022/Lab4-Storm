# STORM

This lab asks you to try and set up a simple Storm topology.

Note, maven must be installed and configured

1. Download Storm <http://www.apache.org/dyn/closer.lua/storm/apache-storm-0.10.0/apache-storm-0.10.0.tar.gz>
2. Install the examples
  1. from the storm directory `cd examples/storm-starter`
  1. `mvn clean install -DskipTests=true`
2. Compile the wordcount example
  2. `mvn compile exec:java -Dstorm.topology=storm.starter.WordCountTopology` 
  1. Or use `bin/storm jar examples/storm-starter/target/storm-*.jar  storm.starter.ExclamationTopology`
# Questions

1. Where does the data come from?
2. How would you modify this code to make it case-insensitive?

