
#Spring Boot + Sonarqube(docker)

```shell script
docker pull sonarquebe
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
docker start sonarqube
docker stop sonarqube
```



- admin 계정 로그인 : admin / admin 

- Administration -> User -> create user -> generate token ( using access to sonarqube )

- project init 

    - application.properties

        - ```properties
            sonar.login={token}
            sonar.host.url=http://localhost:9000
            ```

        - ```xml
            <plugin>
                <groupId>org.sonarsource.scanner.maven</groupId>
                <artifactId>sonar-maven-plugin</artifactId>
            		<version>3.7.0.1746</version>
            </plugin>
            ```
        - mvn sonar:sonar  혹은 
         mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login={token} ( properties에 셋팅하지 않으면..)

