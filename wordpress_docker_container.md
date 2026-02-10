**Creating a wordpress container with its dependencies:**
- container must contain the following dependencies in order to run:
   - LAMP stack:
   - linux
   - apache
   - nginx/relational database eg mySQL
   - php

1- run the command `docker pull wordpress` in CLI to pull the image onto local device
2- run wordpress image and map the port with the command:
 `docker run --name my_website -d -p 5001:80 wordpress`