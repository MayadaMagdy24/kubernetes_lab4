# kubernetes_lab4
Persistent Volumes:
Create a PersistentVolume named cool-volume backed by a hostPath /tmp/my-cool-vol with size 100Mi in the default namespace, set it's storageClassName to “”
![Screenshot (1192)](https://user-images.githubusercontent.com/93229250/235011707-bfef18c7-67c5-458d-a2ce-d170e0697fb5.png)
![Screenshot (1191)](https://user-images.githubusercontent.com/93229250/235011695-f71cc650-0764-4c55-a96f-aa43f7b89bf1.png)

Create a PersistentVolumeClaim named my-claim that requests a volume of size 100Mi , make sure the storageClassName is “” so Kubernetes will match our Claim to the volume we created earlier.
![Screenshot (1195)](https://user-images.githubusercontent.com/93229250/235012139-759076f2-e003-48d9-8a15-801dbd12e18e.png)
![Screenshot (1196)](https://user-images.githubusercontent.com/93229250/235012160-a1f8657d-ed39-4381-9a13-a282604edb4e.png)

Create a pod named pvc-user in namespace default that mounts your PVC my-claim under /mnt/share/my-pvc . Use the image nginx
![Screenshot (1200)](https://user-images.githubusercontent.com/93229250/235012995-188c77c5-5698-4346-a7c1-6cac3894bdc4.png)
![Screenshot (1201)](https://user-images.githubusercontent.com/93229250/235013202-43331507-4534-4af2-abad-e5f51b60c5df.png)
![Screenshot (1206)](https://user-images.githubusercontent.com/93229250/235014209-b3b3a2a0-660e-4c70-bd36-afb5a716a3be.png)

ConfigMaps:
Create a file on your system on /opt/cm.yaml with content:

apiVersion: v1
data:
  tree: birke
  level: "3"
  department: park
kind: ConfigMap
metadata:
  name: birke
![Screenshot (1209)](https://user-images.githubusercontent.com/93229250/235015374-a7ee1daf-3d7c-47fd-8c77-fa86ea85246e.png)

Create a ConfigMap named trauerweide with content tree=trauerweide
![Screenshot (1213)](https://user-images.githubusercontent.com/93229250/235015796-2b4d80dc-b3fb-4f5b-93ac-4bdcd62bd401.png)
![Screenshot (1212)](https://user-images.githubusercontent.com/93229250/235015807-09c27a85-f806-460f-a47b-0a9a725a5264.png)

Create a Pod named pod1 of image nginx:alpine and make key tree of ConfigMap trauerweide available as environment variable TREE1 also Mount all keys of ConfigMap birke as volume. The files should be available under /etc/birke/*
![Screenshot (1217)](https://user-images.githubusercontent.com/93229250/235016361-68021175-ed48-4a68-a400-1babf73aba0b.png)
![Screenshot (1216)](https://user-images.githubusercontent.com/93229250/235016374-d1473496-ec6a-416a-a606-95b83577f848.png)
![Screenshot (1221)](https://user-images.githubusercontent.com/93229250/235018115-ff5c1bf0-5c8a-4340-8a0b-5e92269c829b.png)

