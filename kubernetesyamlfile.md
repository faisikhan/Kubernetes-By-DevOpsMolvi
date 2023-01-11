==================================================================================================        
    In this tutorial, we'll learn about the structure of the Kubernetes YAML File.
==================================================================================================        

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
==================================================================================================        
==================================================================================================        

apiVersion ====================>  Kubernetes API's Version to create objects.
kind       ====================>  What kind of object you want to create.
metadata   ====================>  This data helps us to identify the objects, it includes the name, lables etc.
spec       ====================>  The desired state of the object.


