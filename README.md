Éste es un conjunto aplicaciones de ejemplo y herramientas para el curso de
Docker Swarm de Platzi por Guido Vilariño.

Encuentra más información en https://platzi.com, suscríbete al curso y aprende a
usar Docker para servir tus aplciaciones en un entorno escalable y de alta
disponibilidad que puede escalar a millones de usuarios de manera profesional.


cleaner
docker service create -d \
-e CLEAN_PERIOD=900 \
-e DELAY_TIME=600 \
--log-driver json-file \
--log-opt max-size=1m \
--log-opt max-file=2 \
--name=cleanup \
--mode global \
--mount type=bind,source=/var/run/docker.sock,target=/var/run/docker.sock \
meltwater/docker-cleanup