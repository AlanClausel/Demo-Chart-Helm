# 📦 Helm Chart - demo-chart

Este Helm Chart despliega un servidor NGINX en Kubernetes de forma parametrizable. Permite definir fácilmente la imagen, el número de réplicas, el tipo de servicio y la configuración del Ingress.

---

📋 Prerrequisitos
Antes de instalar este chart, asegurate de tener lo siguiente:

✅ Helm 3 instalado en tu entorno.

✅ Un clúster de Kubernetes funcionando (se recomienda Minikube).

✅ kubectl configurado y conectado al clúster.

✅ (Opcional) Ingress Controller habilitado si se desea usar ingress.enabled: true.

---

## ⚙️ Instalación

### Con valores por defecto:

```bash
helm install demo-nginx ./demo-chart
```

### Con valores por archivo modificado:

```bash
helm install demo-nginx ./demo-chart -f my-values.yaml
```
## 🧩 Valores modificables

| Clave                 | Descripción                                          | Valor por defecto |
| --------------------- | ---------------------------------------------------- | ----------------- |
| replicaCount          | Número de réplicas del Deployment                    | 2                 |
| image.repository      | Repositorio de la imagen                             | nginx             |
| image.tag             | Tag de la imagen                                     | alpine            |
| image.pullPolicy      | Política de descarga de imagen                       | IfNotPresent      |
| service.type          | Tipo de servicio (ClusterIP, NodePort, LoadBalancer) | ClusterIP         |
| service.port          | Puerto del servicio                                  | 80                |
| ingress.enabled       | Habilita el Ingress                                  | true              |
| ingress.hosts\[].host | Host utilizado por el Ingress                        | demo.local        |

---
### Validacion del Chart:
```bash
helm lint ./demo-chart
```

### Agregar la IP al archivo /etc/hosts: (es la IP de mi vagrant, verificar el de tu maquina si es necesario)
```bash
192.168.49.2  demo.local
```

### Acceder a la aplicación:
```bash
http://demo.local
```

## 🧹 Desistalar aplicación:
```bash
helm uninstall demo-nginx
```



