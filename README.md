<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.wpg</groupId>
    <artifactId>local-water-parent</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>pom</packaging>


    <modules>
        <!-- 公共模块 -->
        <module>local-water-common</module>
        <!-- app前台管理服务 -->
        <module>local-water-api</module>

		<!-- 统计分析 独立jar-->
		<module>local-water-statistic</module>
        <!-- 统计分析 独立jar 依赖common-->
        <!--
		<module>local-water-statistic-common</module>
		-->

		<module>local-water-app</module>
        <module>local-water-jgap</module>
        <module>local-water-thirdinteraction</module>
        <module>local-water-alarm</module>
        <module>local-water-realtime</module>
        <!--<module>local-water-bigscreen</module>-->
        <!--<module>local-water-app-common</module>-->

    </modules>


    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
        <java.version>1.8</java.version>

        <spring.boot.version>1.5.9.RELEASE</spring.boot.version>
        <org.apache.maven.compiler>3.7.0</org.apache.maven.compiler>

        <util.restful.swagger>2.7.0</util.restful.swagger>
        <util.apache.commons.lang3>3.5</util.apache.commons.lang3>
        <mybatisplus-spring-boot-starter.version>1.0.5</mybatisplus-spring-boot-starter.version>
        <mybatisplus.version>2.1.8</mybatisplus.version>
        <org.apache.velocity.version>2.0</org.apache.velocity.version>
        <org.modelmapper.verion>1.1.1</org.modelmapper.verion>
        <io.jsonwebtoken.version>0.9.0</io.jsonwebtoken.version>
        <com.xiaoleilu.hutool.version>3.1.2</com.xiaoleilu.hutool.version>
        <org.mockito.version>2.11.0</org.mockito.version>
        <httpclient.version>4.5</httpclient.version>
        <commons-io.version>2.4</commons-io.version>
        <commons-fileupload.version>1.3.1</commons-fileupload.version>
        <org.eclipse.paho.version>1.2.0</org.eclipse.paho.version>
        <com.alibaba.fastjson.version>1.2.45</com.alibaba.fastjson.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-actuator-docs</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-devtools</artifactId>
            <scope>runtime</scope>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.httpcomponents</groupId>
            <artifactId>fluent-hc</artifactId>
            <version>${httpclient.version}</version>
        </dependency>
        <dependency>
            <groupId>commons-net</groupId>
            <artifactId>commons-net</artifactId>
            <version>3.6</version>
        </dependency>
    </dependencies>

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-parent</artifactId>
                <version>${spring.boot.version}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>

    <build>
        <plugins>
            <!-- Spring boot maven多项目打包时需要手动覆盖maven jar plugin -->
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <version>${spring.boot.version}</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>repackage</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>${org.apache.maven.compiler}</version>
                <configuration>
                    <source>${java.version}</source>
                    <target>${java.version}</target>
                </configuration>
            </plugin>
        </plugins>
    </build>




</project>
