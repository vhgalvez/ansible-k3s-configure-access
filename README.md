# 🔐 Ansible: Configurar Acceso Remoto a Clúster K3s con JWT

Este repositorio contiene un playbook de Ansible que automatiza la configuración de acceso remoto al clúster Kubernetes (K3s) desde un nodo externo o controlador. 

## 📦 Características

- Copia un token JWT desde el primer nodo master
- Genera un archivo `kubeconfig` personalizado
- Verifica el acceso mediante `kubectl get nodes`
- Soporte para entornos con VIP configurado (ej: HAProxy + Keepalived)

## 🛠️ Requisitos

- Clúster K3s funcionando
- Ansible ≥ 2.9
- Acceso SSH a los nodos master y al nodo controlador
- El binario de `kubectl` debe estar disponible en el nodo controlador

## 🚀 Uso

```bash
sudo ansible-playbook -i inventory playbooks/configure_k8s_access.yml
```
# 🔐 Ansible: Configurar Acceso Remoto a Clúster K3s con JWT

Este repositorio contiene un playbook de Ansible que automatiza la configuración de acceso remoto al clúster Kubernetes (K3s) desde un nodo externo o controlador. 

## 📦 Características

- Copia un token JWT desde el primer nodo master
- Genera un archivo `kubeconfig` personalizado
- Verifica el acceso mediante `kubectl get nodes`
- Soporte para entornos con VIP configurado (ej: HAProxy + Keepalived)

## 🛠️ Requisitos

- Clúster K3s funcionando
- Ansible ≥ 2.9
- Acceso SSH a los nodos master y al nodo controlador
- El binario de `kubectl` debe estar disponible en el nodo controlador
