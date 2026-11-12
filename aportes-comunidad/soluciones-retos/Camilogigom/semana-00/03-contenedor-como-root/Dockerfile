# 🚨 RETO 3 DOCKER: El contenedor que corre como root (Falla en Kubernetes Seguro) 🚨
#
# Síntoma:
# 1. Al correr 'docker run --rm reto-root whoami', verás que responde 'root' (UID 0).
# 2. Al aplicar este Pod en Kubernetes con políticas de seguridad estrictas (pod-seguro.yaml),
#    el Pod falla con error:
#    'CreateContainerConfigError: container has runAsNonRoot and image will run as root'
#
# Pista:
# Para cumplir con las mejores prácticas de seguridad de contenedores (Least Privilege),
# debes:
# 1. Crear un grupo y un usuario no privilegiado (ej. 'appuser' con UID 10001).
# 2. Asignar los archivos al usuario usando '--chown' en la instrucción COPY.
# 3. Declarar la instrucción 'USER' antes de ejecutar el comando CMD.

FROM python:3.12-alpine

WORKDIR /app

# ❌ ERROR: Copia el archivo como root y no define un usuario no privilegiado
# Fallo: el contenedor corría como root (whoami = root, es_root true)
# Lo descubrí con: docker run --rm reto-docker-03 whoami
# Arreglo: crear appuser (UID 10001), copiar con --chown y USER appuser
RUN addgroup -g 10001 -S appgroup && \
    adduser -u 10001 -S appuser -G appgroup

COPY --chown=appuser:appgroup app.py .
USER appuser 
EXPOSE 8080

CMD ["python", "app.py"]
