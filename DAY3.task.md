# Creating a project "my-docker-app"
## cd my-docker-app
## Install npm
![Screenshot from 2025-03-20 16-31-45](https://github.com/user-attachments/assets/0908cb5b-f923-498b-bb8f-caf739de76af)
# Pull the docker image
## Build the image
![Screenshot from 2025-03-20 16-32-44 (1)](https://github.com/user-attachments/assets/61814770-0cfd-4dd1-977a-c89a7445bc47)
# Exit the project "my-docker-app" using cd ..
## Start the minikube
![Screenshot from 2025-03-20 16-32-59](https://github.com/user-attachments/assets/139cc923-ef4a-406f-a7bd-3ad7b695a446)
# Open the file nginx-deployment.yaml
## paste the code
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app
        image: santhapriyan/docker:latest
        imagePullPolicy: IfNotPresent
        ports:
        - containerPort: 80
```
# Also open service.yaml
## paste the code
```
apiVersion: v1
kind: Service
metadata:
  name: my-app
  namespace: default
spec:
  type: NodePort  # Ensures external access via a specific port
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80       # Service port inside the cluster
      targetPort: 80  # The container's port
      nodePort: 30391   # Externally accessible port
```
# Get pods using kubectl
![Screenshot from 2025-03-20 16-33-29](https://github.com/user-attachments/assets/86981985-ec1a-46ca-89e2-ff99b8ce82d5)
# Get the url using minikube service
![Screenshot from 2025-03-20 16-33-41](https://github.com/user-attachments/assets/fff34bb3-104f-4890-a4cc-c8f75d9900ff)
# Paste the url with using curl
![Screenshot from 2025-03-20 16-34-26](https://github.com/user-attachments/assets/d3af66cc-58f1-44cb-938c-38e144d701f1)
# Open the url:http//192.168.2:30391
![Screenshot from 2025-03-20 16-34-42](https://github.com/user-attachments/assets/7e27449b-bb2d-42ef-ac4e-bf493bfa8ab6)


