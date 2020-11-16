# STORM

This lab asks you to try and set up a simple Storm topology.

<!--Note, maven must be installed and configured-->

# Storm: install and run your first topology

1. Download binary from the internet (using a mirror site)

`$ wget https://mirrors.whoishostingthis.com/apache/storm/apache-storm-2.2.0/apache-storm-2.2.0-src.tar.gz`

2. Unzip STORM binary (in current directory, use `$ -C ~/<dirname> ` to unzip in a different directory `<dirname>` under user home folder)

`$ tar -xvzf apache-storm-2.2.0-src.tar.gz `

3. If you do not have Maven installed and configure:
  - on Unix/Linux: `$ sudo apt-get install maven`
  - on Mac: `$ brew install maven`
  - check it installed correctly: `$ mvn -version`
  
4. Go into the storm-starter project within the examples folder: `$ cd examples/storm-starter`

5. Compile the jar files: `$ mvn clean install -DskipTests=true`
   - Note: it should take a few minutes, and you’ll see a lot of output with "Build Success" in the end

6. Run the workdcount topology example (previously compiled)
  - `$ mvn compile exec:java -Dstorm.topology=storm.starter.WordCountTopology` 

Let's now have a look at the details of what happened when you run the topology, where are the files and what do they look like [here](http://www.haroldnguyen.com/blog/2015/01/setting-up-storm-and-running-your-first-topology/)
<!--On a cluster: `$ bin/storm jar examples/storm-starter/target/storm-*.jar  storm.starter.ExclamationTopology`-->

## Note that to run a topology on a cluster you first need to run the cluster
Check how to deploy Storm in production in the final part of [this tutorial](http://www.haroldnguyen.com/blog/2015/01/setting-up-storm-and-running-your-first-topology/)

## Note on Maven sources and target folders
Technically, any directory that contains a pom.xml file is also a valid Maven project. A pom.xml file contains everything needed to describe your Java project.
Apart from a pom.xml file, you also need Java source code for Maven to do its magic, whenever you are calling mvn clean install. By convention:
   - Java source code is to be meant to live in the "/src/main/java" folder
   - Maven will put compiled Java classes into the "target/classes" folder
   - Maven will also build a .jar or .war file, depending on your project, that lives in the "target" folder.

Your project will look like this:
+ `$ storm-starter/src/jvm/org/apache/storm/starter/WordCountTopology.java`
+ `$ storm-starter/target/classes/org/apache/storm/starter/WordCountTopology.class` (after 'mvn compile')
+ `$ storm-starter/target/storm-starter-2.2.0.jar` (upon mvn package or mvn install)



<!-- see maven details at https://www.marcobehler.com/guides/mvn-clean-install-a-short-guide-to-maven
# Questions
1. Where does the data come from?
2. How would you modify this code to make it case-insensitive?
-->
