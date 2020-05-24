# Задача № 1 "Синдром 100%"

## Краткое описание

1. Создан maven проект.
2. Перенесен код из лекции 
3. Настроен JaCoCo plugin:
    * Элемент BUNDLE
    * Счетчик BRANCH
        * Значение COVEREDRATIO 100%  
              
## Код

```xml
<plugin>
    <groupId>org.jacoco</groupId>
    <artifactId>jacoco-maven-plugin</artifactId>
    <version>0.8.5</version>
    <executions>
        <execution>
            <id>default-prepare-agent</id>
            <goals>
                <goal>prepare-agent</goal>
            </goals>
        </execution>
        <execution>
            <id>default-report</id>
            <goals>
                <goal>report</goal>
            </goals>
        </execution>
        <execution>
            <id>default-check</id>
            <goals>
                <goal>check</goal>
            </goals>
            <configuration>
                <rules>
                    <rule>
                        <element>BUNDLE</element>
                        <limits>
                            <limit>
                                <counter>BRANCH</counter>
                                <value>COVEREDRATIO</value>
                                <minimum>100%</minimum>
                            </limit>
                        </limits>
                    </rule>
                </rules>
            </configuration>
        </execution>
    </executions>
</plugin>    
```

## Лог
```
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running ru.netology.statistic.StatisticsServiceTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.053 s - in ru.netology.statistic.StatisticsServiceTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ statistics ---
[INFO] 
[INFO] --- jacoco-maven-plugin:0.8.5:report (default-report) @ statistics ---
[INFO] Loading execution data file C:\Users\79994\IdeaProjects\j2.5.1\target\jacoco.exec
[INFO] Analyzed bundle 'statistics' with 1 classes
[INFO] 
[INFO] --- jacoco-maven-plugin:0.8.5:check (default-check) @ statistics ---
[INFO] Loading execution data file C:\Users\79994\IdeaProjects\j2.5.1\target\jacoco.exec
[INFO] Analyzed bundle 'statistics' with 1 classes
[INFO] All coverage checks have been met.
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  5.971 s
[INFO] Finished at: 2020-05-24T12:58:15+07:00
[INFO] ------------------------------------------------------------------------
```