# 📔 Bitácora de Aprendizaje — 🌐 Semana 03: Redes en Kubernetes (Services y Gateway API)

> ⛵ **Tripulante:** [`@Arlex0296`](https://github.com/Arlex0296)  
> 🗓️ **Fecha de registro:** `2026-11-27`  
> 🎓 **Portafolio Principal:** [⬅️ Volver a mi Portafolio Profesional K8s](../README.md)

---

## 1️⃣ 💡 ¿Qué aprendí esta semana?

En ese tema se aprende cómo se comunican los pods entre sí y cómo llega el tráfico desde fuera

---

## 2️⃣ 🧩 ¿Qué fue lo más retador y cómo lo resolví?

La  comunicación de estos entre  si  los pod

---

## 3️⃣ 💻 Comandos y herramientas que practiqué

```bash
k get svc                        
k get svc -o wide                
k describe svc <nombre>           
k get endpoints <nombre>           
k get endpointslices            
k expose deployment web --port=80 --target-port=8080                
k expose deployment web --port=80 --type=NodePort                
k expose deployment web --port=80 --type=LoadBalancer
```

---

## 4️⃣ 🚀 Aplicación real y próximos pasos

Mejorando  los proyectos  que hay en mi empresa

---

<div align="center">
  <sub>🏔️☕ Bitácora registrada en <b><a href="https://github.com/edwinbermudez91/Fundamentos-Kubernetes">De Cero a Capitán en Kubernetes — Cloud Native Medellín (CNCF)</a></b></sub>
</div>
