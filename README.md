# Getting Started

## Windows

### Compile, Test, jar Code
* ./gradlew.bat clean build

### Run Jar
* Local:      ./mvnw.cmd spring-boot:run 
* Background: nohup bash mvnw.cmd spring-boot:run &

### Testing Application
* Abrir navegador: http://localhost:8081/rest/mscovid/test?msg=testing

## Linux

### Compile, Test, jar Code
* ./gradlew.bat clean build

### Run Jar
* Local:      ./mvnw spring-boot:run 
* Background: nohup bash mvnw spring-boot:run &

### Testing Application
* curl -X GET 'http://localhost:8081/rest/mscovid/test?msg=testing'
#### Using Docker to test this app.
```bash
### Compile Code
docker run -it --rm -v $(pwd):/code --workdir /code maven mvn clean compile -e

### Test Code
docker run -it --rm -v $(pwd):/code --workdir /code maven mvn clean test -e

### Jar Code
docker run -it --rm -v $(pwd):/code --workdir /code maven mvn clean package -e

### Run Jar
docker run -it --rm -p 8082:8081  -v $(pwd):/code --workdir /code maven ./mvnw spring-boot:run

### test