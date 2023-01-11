       
In this tutorial, we'll learn about the structure of the Kubernetes YAML File. Consider the example of the following YAML file.
        
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
        - containerPort: 80  
      

1. apiVersion ====================>  Kubernetes API's Version to create objects.
2. kind       ====================>  What kind of object you want to create.
3. metadata   ====================>  This data helps us to identify the objects, it includes the name, lables etc.
4. spec       ====================>  The desired state of the object.




