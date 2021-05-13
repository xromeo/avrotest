#Compiling and running the example code
From this directory, execute the following commands to build and run the example:

$ mvn compile # includes code generation via Avro Maven plugin
$ mvn -q exec:java -Dexec.mainClass=com.avro.example.Main

#Beta feature: Generating faster code
In this release we have introduced a new approach to generating code that speeds up decoding of objects by more than 10% and encoding by more than 30% (future performance enhancements are underway). To ensure a smooth introduction of this change into production systems, this feature is controlled by a feature flag, the system property org.apache.avro.specific.use_custom_coders. In this first release, this feature is off by default. To turn it on, set the system flag to true at runtime. In the sample above, for example, you could enable the fater coders as follows:

$ mvn -q exec:java -Dexec.mainClass=example.SpecificMain \
    -Dorg.apache.avro.specific.use_custom_coders=true



--------------------------------
#Compiling and running the example code 2
$ mvn compile
$ mvn -q exec:java -Dexec.mainClass=com.avro.example.Main2 -Dorg.apache.avro.specific.use_custom_coders=true