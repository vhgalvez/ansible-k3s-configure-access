# Ansible: Configurar Acceso Externo al Clúster K3s

Este repositorio automatiza la creación del archivo `kubeconfig` en el nodo de administración externo ("controller") para conectarse a un clúster K3s de alta disponibilidad a través del VIP expuesto por HAProxy + Keepalived.

---

## 🧱 Componentes

Este playbook realiza las siguientes tareas:

1. **Obtención del Token JWT**: Recupera el token JWT desde el nodo `master1` (`10.17.4.21`).
2. **Creación del Kubeconfig**: Genera el archivo `kubeconfig` apuntando al VIP del API Server (`10.17.5.10:6443`).
3. **Verificación de Conectividad**: Comprueba la conectividad con el clúster mediante el comando `kubectl get nodes`.

---

## 📂 Estructura del Repositorio

El repositorio está organizado de la siguiente manera:

```plaintext
inventory/
├── hosts.ini               # Definición de grupos y nodos
playbooks/
├── configure_k3s_access.yml # Playbook principal para configurar el acceso
```

---

## 🚀 Uso

Sigue estos pasos para ejecutar el playbook:

1. Asegúrate de cumplir con los requisitos previos (ver sección de requisitos).
2. Ejecuta el siguiente comando desde la raíz del repositorio:

   ```bash
   sudo ansible-playbook -i inventory/hosts.ini playbooks/install_access.yml
   ```

---

## 🔐 Requisitos

Antes de ejecutar el playbook, asegúrate de que:

- **Clúster K3s**: El clúster K3s en alta disponibilidad ya está desplegado.
- **Token JWT**: El token JWT está disponible en `/tmp/traefik-token.jwt` en el nodo `master1`.
- **VIP Configurado**: El VIP (`10.17.5.10`) está configurado y accesible desde el nodo `controller`.

---

## ✅ Próximos Pasos

¿Quieres que prepare los siguientes archivos para este repositorio?

- `README.md` (este archivo)
- `.gitignore`
- `LICENSE`

O, si lo prefieres, ¿quieres integrarlo como un **submódulo o rol reutilizable** dentro de tu ecosistema FlatcarMicroCloud (`vhgalvez/`)?

¡Hazme saber cómo puedo ayudarte a continuar!