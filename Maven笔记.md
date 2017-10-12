##Maven笔记

* 修改Maven编译JDK版

1.修改maven目录下conf/settings.xml
	
```
	<profile>

    <id>jdk-1.7</id>

    <activation>

        <activeByDefault>true</activeByDefault>

        <jdk>1.7</jdk>

    </activation>

    <properties>

        <maven.compiler.source>1.7</maven.compiler.source>

        <maven.compiler.target>1.7</maven.compiler.target>

        <maven.compiler.compilerVersion>1.7</maven.compiler.compilerVersion>

    </properties>

</profile>
```

  2.针对项目修改其中的pom.xml文件，然后用maven命令行执行(mvn clean, mvn package)，即可获得指定jdk版本编译的jar包
     
```
<build>

<plugins>

<plugin>

<groupId>org.apache.maven.plugins</groupId>

<artifactId>maven-compiler-plugin</artifactId>

<configuration>

<source>1.7</source>

<target>1.7</target>

<encoding>${file_encoding}</encoding>

</configuration>

</plugin>

</plugins>

</build>
```
  3.本工程修改仓库地址pom.xml添加
  
```
<repositories>
    <repository>
        <id>central</id>
        <name>Central Repository</name>
        <url>http://maven.aliyun.com/nexus/content/repositories/central</url>
        <layout>default</layout>
        <snapshots>
            <enabled>false</enabled>
        </snapshots>
    </repository>
</repositories>
```