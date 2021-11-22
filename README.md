# Helm-Wordpress-MariaDB-Ingress-Controller-GBL

1- I created a kubernetes cluster on GCP called gbl-cluster.

<img width="1148" alt="Screen Shot 2021-11-22 at 10 47 22 AM" src="https://user-images.githubusercontent.com/57590298/142891759-31956c37-020c-41a9-a381-cafde13d685f.png">

2- I created a namespace called gblenv.

<img width="664" alt="Screen Shot 2021-11-22 at 10 49 43 AM" src="https://user-images.githubusercontent.com/57590298/142892126-97b52ffc-b615-42dc-aee4-9511631f35e2.png">

3- Regarding the assigniment requirements:

3.1- Wordpress: I added the "bitnami/wordpress" to my repo list of Helm, using the command "helm add repo gblwordpress https://charts.bitnami.com/bitnami". The WordPress version is the most recent one that I found (12.2.0).

<img width="851" alt="Screen Shot 2021-11-22 at 10 59 37 AM" src="https://user-images.githubusercontent.com/57590298/142893952-73cbd949-7b31-4c47-bc2f-880f699c56ea.png">

3.2- Setting up username and password for WordPress, inside of the "gbl/" folder there is a file called "wordpress-values.yaml" where you can find all information regarding user and password.

![Screen Shot 2021-11-22 at 11 07 35 AM](https://user-images.githubusercontent.com/57590298/142895247-05cea544-1242-4f79-baec-11fc00c5b549.png)

3.3- Install wordpress chart with the user values. Using the command "helm install gblwordpress gbl/wordpress --values=wordpress-values.yaml --namespace=gblenv --version 12.2.0"

3.4- Ingress Controller: Same as I did on step 3.1, I added the "ingress-nginx" to my helm repo using command "helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx"

<img width="595" alt="Screen Shot 2021-11-22 at 11 19 52 AM" src="https://user-images.githubusercontent.com/57590298/142897016-32d3bbbb-c16e-4320-a5f3-b1ec41de942c.png">

4- Requirements:

4.1- All yaml's files used are inside the "gbl" folder.

4.2- Screenshots of the ingress and service running (services and pods)

<img width="780" alt="Screen Shot 2021-11-22 at 11 28 53 AM" src="https://user-images.githubusercontent.com/57590298/142898474-e92916a0-199c-44f7-aae1-67bceb404e0a.png">

<img width="954" alt="Screen Shot 2021-11-22 at 11 29 35 AM" src="https://user-images.githubusercontent.com/57590298/142898602-1b312206-e034-4338-a97e-fc79754a4d6b.png">

<img width="793" alt="Screen Shot 2021-11-22 at 11 30 53 AM" src="https://user-images.githubusercontent.com/57590298/142898814-2405d69b-0504-4523-b16c-d511709a36ff.png">

4.3- Screenshot of pods logs

<img width="1430" alt="Screen Shot 2021-11-22 at 11 34 22 AM" src="https://user-images.githubusercontent.com/57590298/142899356-797552d0-47ac-4c2e-b1a0-2ff3549b25a5.png">kubectl -n gblenv logs gbl-ingress-nginx-ingress-759d974b8b-vpflv


<img width="788" alt="Screen Shot 2021-11-22 at 11 36 18 AM" src="https://user-images.githubusercontent.com/57590298/142899664-4db455f0-eb2d-453d-a8b5-42d745210711.png">  kubectl -n gblenv logs gblwordpress-8546788cd6-z76jc


<img width="1107" alt="Screen Shot 2021-11-22 at 11 38 19 AM" src="https://user-images.githubusercontent.com/57590298/142899991-fc643ce6-0410-4a77-b5eb-2cc3eb20dbfd.png">kubectl -n gblenv logs gblwordpress-mariadb-0

4.4- The main page of the Wordpress in a browser (screenshot):

<img width="452" alt="Screen Shot 2021-11-22 at 11 39 31 AM" src="https://user-images.githubusercontent.com/57590298/142900167-60ad6941-a70b-47e9-b459-45bccc260dc2.png">      Login page

<img width="1430" alt="Screen Shot 2021-11-22 at 11 40 45 AM" src="https://user-images.githubusercontent.com/57590298/142900377-6b071ad5-59af-432d-9d22-41892f940b93.png"> Dashboard page





