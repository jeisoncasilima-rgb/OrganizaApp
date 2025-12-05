## 📱 OrganizaApp

**OrganizaApp** es una **aplicación móvil Android** desarrollada para la gestión eficiente de tareas personales, permitiendo a los usuarios crear, organizar y realizar seguimiento de sus tareas diarias mediante una interfaz moderna e intuitiva.

---

## ✨ Funcionalidades principales

* Crear, editar y eliminar tareas.
* Organizar tareas por **categorías personalizadas**.
* Establecer **prioridades** (Alta, Media, Baja).
* Filtrar tareas.
* Marcar tareas como completadas.

---

## 🛠️ Instrucciones de instalación y ejecución

### Prerrequisitos
* Dispositivo físico con **Android 8.0 o superior**.

### Pasos de instalación por APK manualmente
1. Transferir el archivo **APK** al dispositivo.
2. Habilitar **"Orígenes desconocidos"** en Ajustes de seguridad.
3. Ejecutar el archivo APK e instalar.

---

## 💻 Tecnologías y librerías utilizadas

### Lenguaje y Frameworks
* **Kotlin** - Lenguaje de programación principal.
* **Jetpack Compose** - Framework de UI declarativa.
* **Android SDK** - Plataforma de desarrollo móvil.

### Componentes de Android Jetpack

| Componente | Versión | Propósito |
| :--- | :--- | :--- |
| **Room** | 2.6.1 | Persistencia de base de datos local |
| **ViewModel** | 2.7.0 | Gestión del ciclo de vida de la UI |
| **Navigation Compose** | 2.7.6 | Navegación entre pantallas |
| **Material3** | 1.2.0 | Sistema de diseño y componentes UI |

### Dependencias principales
* `implementation ("androidx.compose.ui:ui:1.6.0")`
* `implementation ("androidx.compose.material3:material3:1.2.0")`
* `implementation ("androidx.activity:activity-compose:1.8.2")`
* `implementation ("androidx.lifecycle:lifecycle-viewmodel-compose:2.7.0")`
* `implementation ("androidx.navigation:navigation-compose:2.7.6")`
* `implementation ("androidx.room:room-runtime:2.6.1")`
* `implementation ("androidx.room:room-ktx:2.6.1")`
* `kapt ("androidx.room:room-compiler:2.6.1")`
* `implementation ("org.jetbrains.kotlinx:kotlinx-coroutines-android:1.7.3")`

---

## 🏗️ Patrones de diseño implementados

### 1. MVVM (Model-View-ViewModel)
* **Implementación:**
    * **Model:** Entidades Room (`Task`, `Category`) y Repository.
    * **View:** Composables (`TaskListScreen`, `AddTaskScreen`, `CategoryManagerScreen`).
    * **ViewModel:** `TaskViewModel` y `CategoryViewModel`.
* **Justificación:** Separa la lógica de negocio de la interfaz de usuario...

### 2. Repository Pattern
* **Implementación:**
    * Clase `TaskRepository` que centraliza el acceso a datos.
    * Abstracción entre ViewModel y fuentes de datos.
* **Justificación:** Proporciona una API limpia para operaciones de datos...

### 3. Singleton Pattern
* **Implementación:**
    * `TaskRepository` implementado como Singleton.
    * Instancia única accesible globalmente mediante `getInstance()`.
* **Justificación:** Garantiza una única instancia del Repository en toda la app...

### 4. Observer Pattern
* **Implementación:**
    * Uso de **StateFlow** en ViewModels para observar cambios de estado.
    * Composables que reaccionan a cambios en los flujos de datos.
* **Justificación:** Actualización automática de la UI cuando cambian los datos...

### 5. Factory Pattern
* **Implementación:**
    * `ViewModelFactory` para la creación de instancias de ViewModel.
    * Inyección de dependencias en los ViewModels.
* **Justificación:** Centraliza la lógica de creación de ViewModels...
