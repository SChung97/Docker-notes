**Prerequisites:**
- Dockerfile - make a dockerfile within images folder, where all automation code will be written

1- what base image will be used?
2- what do you want in the image?
3- what ports will the image need to be able to us? - must be placed at the bottom of the file, to set up connection last
4- launch the server

- each command in the file becomes a separate layer of the image
- Dockerfile uses instruction argument format

**Dockerfile:**
FROM nginx

COPY index.html /usr/share/nginx/html
COPY css.css /usr/share/nginx/html

EXPOSE 80 (to enable nginx to run on port 80)

CMD ["nginx", "-g", "daemon off;"]

1- save the Dockerfile script in the images folder containing your html and css files

2- run the command `docker build . -t schung97/cv_automated_image`

3- run the container `docker run -d -p 80:80 schung97/cv_automated_image`

**Reducing memory required to run the container:**
- can use nginx alpine version or even nginx slim
- for very simple containers, the two can actually be combined
- can be done by adding the tag alpine-slim into Dockerfile `FROM nginx:alpine-slim`
- run the build but change the name: `docker build . -t schung97/cv_automated_image_slim`
- has reduced the container size from 237MB to 20MB
- may not work if a container has certain dependencies