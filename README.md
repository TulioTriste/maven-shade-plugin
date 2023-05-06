# maven-shade-plugin

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-shade-plugin</artifactId>
    <version>3.0.0</version>
    <executions>
        <execution>
            <phase>package</phase>
            <goals>
                <goal>shade</goal>
            </goals>
        </execution>
    </executions>
    <configuration>
        <createDependencyReducedPom>false</createDependencyReducedPom>
        <shadedArtifactAttached>false</shadedArtifactAttached>

        <!-- remove unused classes -->
        <minimizeJar>true</minimizeJar>

        <!-- relocate packages to prevent bug with other own plugins -->
        <relocations>
            <relocation>
                <pattern>com.jonahseguin.drink</pattern>
                <shadedPattern>me.arjona.balloons.utilities.drink</shadedPattern>
            </relocation>

            <relocation>
                <pattern>me.arjona.customutilities</pattern>
                <shadedPattern>me.arjona.balloons.utilities</shadedPattern>
            </relocation>
        </relocations>
    </configuration>
</plugin>
```
