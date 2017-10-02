# Migrating Storm Topologies to Heron

This repository serves as an example of how to migrate existing Storm Topology to run on Heron

1. Change storm-core dependency in project pom.xml to heron-storm
    From:

        <dependency>
            <groupId>org.apache.storm</groupId>
            <artifactId>storm-core</artifactId>
            <version>${storm.version}</version>
        </dependency>

    To:

        <dependency>
            <groupId>com.twitter.heron</groupId>
            <artifactId>heron-storm</artifactId>
            <version>${heron.version}</version>
        </dependency>

2. Clean and Recompile

        mvn clean install

3. Submit Storm Topology to run on Heron

        heron submit local <PROJECT_ROOT>/target/storm-heron-examples-1.0-SNAPSHOT.jar \
        com.streamlio.examples.ExclamationTopology test1