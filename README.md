<a id="readme-top"></a>

[![LinkedIn][linkedin-shield]][linkedin-url]

# Kubernetes Portfolio

This repository contains all the Kubernetes manifests and configuration files needed to deploy and manage my portfolio applications. It includes configurations for deployments, services, ingresses, and any other resources required to run the apps in a Kubernetes environment.

---

**IMPORTANT** _This setup is for development and testing only._

---

# How-to-steps

1. Install these tools, which I would describe as [Kubernetes Infrastructure Components](#kubernetes-infrastructure-components) as they are essential for deploying and managing applications in a kubernetes environment.
2. To deploy the [Notes](https://github.com/daniarmas/notes) app read the [instructions](notes-app/README.md).

# Kubernetes Infrastructure Components

### Ingress-Nginx

An ingress controller for Kubernetes that uses NGINX as a reverse proxy and load balancer to route traffic to the appropriate services, offering features like SSL termination and path-based routing.

1. Add the Ingress Helm repository
   ```sh
   helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
   ```
2. Update Helm
   ```sh
   helm repo update
   ```
3. Finally, run the following command to install the Nginx ingress:
   ```sh
   helm install nginx-ingress ingress-nginx/ingress-nginx --set controller.publishService.enabled=true
   ```
### Cert-Manager

A powerful and extensible X.509 certificate controller for Kubernetes that obtains certificates from various issuers, ensures they are valid and up-to-date, and attempts renewal at a configured time before expiry.

1. Create a namespace for cert-manager
   ```sh
   kubectl create namespace cert-manager
   ```
2. You’ll need to add the [Jetstack Helm repository](https://artifacthub.io/packages/helm/cert-manager/cert-manager) to Helm, which hosts the Cert-Manager chart. To do this, run the following command:
   ```sh
   helm repo add jetstack https://charts.jetstack.io
   ```
3. Then, update Helm’s chart cache
   ```sh
   helm repo update
   ```
4. Finally, install Cert-Manager into the cert-manager namespace by running the following command
   ```sh
   helm install cert-manager jetstack/cert-manager --namespace cert-manager --version v1.10.1 --set installCRDs=true
   ```

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

[Linkedin]([Linkedin](https://www.linkedin.com/in/d3v06/))

<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/daniarmas/notes/blob/main/LICENSE
[linkedin-shield]: https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url]: https://www.linkedin.com/in/d3v06/

[Go.dev]: https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white
[Go-url]: https://go.dev/
[Redis.io]: https://img.shields.io/badge/redis-%23DD0031.svg?&style=for-the-badge&logo=redis&logoColor=white
[Redis-url]: https://redis.io/
[Cockroachlabs.com]: https://img.shields.io/badge/Cockroach%20Labs-6933FF?style=for-the-badge&logo=Cockroach%20Labs&logoColor=white
[Cockroachlabs-url]: https://www.cockroachlabs.com/
