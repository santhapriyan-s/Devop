# Task 5

## Install Maven
```bash
sudo apt install maven
```
![image](https://github.com/user-attachments/assets/a1c7b760-d02d-403d-8213-48898f1ce463)

## Fork the repo on github

![Screenshot (369)](https://github.com/user-attachments/assets/deb85246-0ad6-43a0-95c9-a9f94ddbc414)
)

## Configure Jenkins
 - In Jenkins go to `configure jenkins` > `tools`
 - Locate JDK section
 - Uncheck `Install Automatically`
 - Name `Java 17`
 - Go to terminal and enter the command and get the java 17 path:

```bash
update-java-alternatives --list 
```

 - paste the java path in `JAVA_HOME`

![image](https://github.com/user-attachments/assets/e71ecf62-8ba8-4cf5-8cd5-1ef1e1cb694e)

## Fork The Repo and build the pipeline
![Screenshot from 2025-03-22 14-07-38](https://github.com/user-attachments/assets/de10ae4b-9458-4671-8174-4fe15d8d67eb)
![Screenshot from 2025-03-22 14-21-02](https://github.com/user-attachments/assets/f92de632-40de-425e-856e-04a64d568e28)

