# 📦 Helm Chart - demo-chart

Este Helm Chart despliega un servidor NGINX en Kubernetes de forma parametrizable. Permite definir fácilmente la imagen, el número de réplicas, el tipo de servicio y la configuración del Ingress.

---

## 🚀 Instalación

### Con valores por defecto:

```bash
helm install demo-nginx ./demo-chart

### Con valores por defecto:
```bash
helm install demo-nginx ./demo-chart -f my-values.yaml
