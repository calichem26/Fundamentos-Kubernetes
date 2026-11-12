# 🚨 RETO 1 DOCKER (Nivel Fácil): El contenedor que se apaga solo al instante 🚨
# Síntoma: Haces 'docker build -t reto-docker-01 .' y la imagen compila bien.
#          Sin embargo, al hacer 'docker run -d -p 8080:80 reto-docker-01' y luego 'docker ps',
#          ¡el contenedor NO aparece corriendo!
# Pista: Ejecuta 'docker ps -a' para ver su código de salida.
#        ¿Por qué el proceso de Nginx en CMD se envía a segundo plano y mata al contenedor?
#        Recuerda: en Docker, el proceso principal (PID 1) debe correr en PRIMER PLANO (foreground).

FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80
# Fallo: el contenedor se apagaba apenas arrancaba (Exited 0)
# Lo descubrí con: docker ps -a y docker logs test-reto-01
# Arreglo: nginx en primer plano con daemon off, para que el proceso principal no termine
CMD ["nginx", "-g", "daemon off;"]
