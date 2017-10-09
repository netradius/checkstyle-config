# NetRadius Checkstyle Config

This project contains the checkstyle settings used by NetRadius Java projects. 
These styles are small modifications to those by used by Googles which are 
documented at 

https://google-styleguide.googlecode.com/svn-history/r130/trunk/javaguide.html

To use this checkstyle configuration, add the plugin configuration to your maven
pom.xml file like shown below. You may need to adjust versions as necessary.

    <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-checkstyle-plugin</artifactId>
        <version>2.17</version>
        <executions>
            <execution>
                <id>validate</id>
                <phase>validate</phase>
                <configuration>
                    <configLocation>netradius_checks.xml</configLocation>
                    <encoding>UTF-8</encoding>
                    <sourceDirectory>${project.basedir}/src/</sourceDirectory>
                    <consoleOutput>true</consoleOutput>
                    <failsOnError>true</failsOnError>
                </configuration>
                <goals>
                    <goal>check</goal>
                </goals>
            </execution>
        </executions>
        <dependencies>
            <dependency>
                <groupId>com.netradius</groupId>
                <artifactId>checkstyle-config</artifactId>
                <version>0.0.2-SNAPSHOT</version>
            </dependency>
            <dependency>
                <groupId>com.puppycrawl.tools</groupId>
                <artifactId>checkstyle</artifactId>
                <version>8.1</version>
            </dependency>
        </dependencies>
    </plugin>
