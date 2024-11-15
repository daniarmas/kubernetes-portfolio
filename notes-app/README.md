<a id="readme-top"></a>

[![LinkedIn][linkedin-shield]][linkedin-url]

# Notes App

[Github Project](https://github.com/daniarmas/notes)

[license-url]: https://github.com/daniarmas/notes/blob/main/LICENSE
[linkedin-shield]: https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url]: https://www.linkedin.com/in/d3v06/

# How-to-steps

1. Create the app namespace
   ```sh
   kubectl create namespace notes-app
   ```
2. Install postgres
   ```sh
   kubectl apply -f postgres/.
   ```
2. Install pgadmin
   ```sh
   kubectl apply -f pgadmin/.
   ```