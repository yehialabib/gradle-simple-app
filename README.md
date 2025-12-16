//Use the following command to be able to use ./gradlew commands
gradle wrapper

//build the artifact
./gradlew build

//test the application
java -jar build/libs/gradle-simple-app-1.0.0.jar

//create Nexus container
docker run -d -p 8081:8081 --name nexus sonatype/nexus3

//retrieve admin password to connect to nexus
docker exec -it nexus cat /nexus-data/admin.password

//publish the artifact to Nexus via Gradle
./gradlew publish