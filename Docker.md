# Dcoker

**1. What is Docker?**

---

Docker is a containerization platform that allows you to package an application and its dependencies into a lightweight, portable container. Containers share the host OS kernel but run in isolated environments, which makes them faster and more efficient than virtual machines. Docker ensures consistency across environments (development, staging, production) and simplifies deployment and scaling. It uses Docker images (immutable templates) to create containers, and Dockerfiles to define how images are built.

Docker — это платформа контейнеризации, которая позволяет упаковать приложение и его зависимости в лёгкий переносимый контейнер. Контейнеры используют общее ядро ОС, но работают в изолированной среде, поэтому они быстрее и легче виртуальных машин. Docker обеспечивает одинаковую среду в development, taging и production и упрощает деплой и масштабирование. Он использует Docker images (неизменяемые шаблоны) для создания контейнеров и Dockerfile для описания процесса сборки образа.

**2. What do you understand about containers?**

---

Containers are lightweight, isolated environments that package an application together with its dependencies, libraries, and configuration. They share the host operating system kernel but run as separate processes with their own filesystem, network stack, and resource limits. Containers are portable and consistent, meaning the same container can run reliably across development, testing, and production environments. They start quickly, consume fewer resources than virtual machines, and are commonly used for microservices and scalable architectures.

Контейнеры — это лёгкие изолированные среды, которые упаковывают приложение вместе с его зависимостями, библиотеками и конфигурацией. Они используют общее ядро операционной системы, но работают как отдельные процессы со своей файловой системой, сетью и лимитами ресурсов. Контейнеры обеспечивают переносимость и одинаковую среду выполнения в development, testing и production. Они запускаются быстро, потребляют меньше ресурсов, чем виртуальные машины, и часто используются в микросервисной и масштабируемой архитектуре.

**3. How many Docker components are there?**

---

Docker has three main components:

- Docker Client – The CLI or API that allows users to interact with Docker (e.g., docker build, docker run).

- Docker Daemon (dockerd) – The background service that manages images, containers, networks, and volumes.

- Docker Registry – A storage and distribution system for Docker images (e.g., Docker Hub or a private registry).

The client communicates with the daemon, and the daemon pulls/pushes images from/to the registry.

В Docker есть три основных компонента:

- Docker Client – CLI или API, через которые пользователь управляет Docker (docker build, docker run).

- Docker Daemon (dockerd) – фоновый сервис, который управляет образами, контейнерами, сетями и томами.

- Docker Registry – хранилище и система распространения Docker-образов (например, Docker Hub или приватный registry).

Клиент взаимодействует с daemon, а daemon загружает и отправляет образы в registry.

**4. What is a Docker Image?**

---

A Docker image is a read-only, immutable template used to create containers. It contains the application code, runtime, libraries, dependencies, environment variables, and configuration needed to run the application. Images are built from a Dockerfile and consist of layered filesystems, which makes them efficient and cacheable. When you run an image, Docker creates a container by adding a writable layer on top of the image.

Docker image — это неизменяемый (read-only) шаблон, который используется для создания контейнеров. Он содержит код приложения, runtime, библиотеки, зависимости, переменные окружения и конфигурацию. Образы собираются из Dockerfile и состоят из слоёв (layers), что делает их эффективными и позволяет использовать кэширование. При запуске образа Docker создаёт контейнер, добавляя поверх него записываемый слой.

**5. What is Docker Compose?**

---

Docker Compose is a tool used to define and run multi-container Docker applications. It allows you to configure services, networks, and volumes in a single docker-compose.yml file. With one command (docker-compose up or docker compose up), you can build, start, and manage all containers defined in the configuration. Docker Compose simplifies local development and testing of applications that depend on multiple services (e.g., API + database + cache).

Docker Compose — это инструмент для описания и запуска multi-container приложений в Docker. Он позволяет настроить сервисы, сети и тома в одном файле docker-compose.yml. Одной командой (docker compose up) можно собрать и запустить все контейнеры, описанные в конфигурации. Docker Compose упрощает локальную разработку и тестирование приложений, которые состоят из нескольких сервисов (например, API + база данных + кэш).

**6. What do you understand about Dockerfile? Can you write it?**

---

A Dockerfile is a text file that contains step-by-step instructions for building a Docker image. It defines the base image, working directory, dependencies, environment variables, and the command that runs when the container starts. Each instruction creates a new layer, which allows Docker to cache builds efficiently. Yes, I can write a Dockerfile. For example, for a FastAPI application:

```yml
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

Dockerfile — это текстовый файл с пошаговыми инструкциями для сборки Docker-образа. Он определяет базовый образ, рабочую директорию, зависимости, переменные окружения и команду запуска контейнера. Каждая инструкция создаёт новый слой, что позволяет Docker эффективно использовать кэш.
Да, я могу написать Dockerfile. Например, для FastAPI-приложения — пример приведён выше.

**7. What do you understand about Docker Namespace?**

---

Docker namespaces are a Linux kernel feature that provides isolation between containers.

Namespaces ensure that each container has its own separate view of system resources such as processes, network interfaces, mount points, users, and hostnames.

Docker uses several types of namespaces, including:

PID namespace – isolates process IDs

NET namespace – isolates network interfaces

MNT namespace – isolates filesystem mount points

IPC namespace – isolates interprocess communication

UTS namespace – isolates hostname and domain name

USER namespace – isolates user and group IDs

Together with cgroups (which limit resources like CPU and memory), namespaces form the foundation of container isolation.

Docker namespaces — это механизм ядра Linux, который обеспечивает изоляцию контейнеров.

Namespace позволяет каждому контейнеру иметь собственное представление системных ресурсов: процессов, сети, точек монтирования, пользователей и имени хоста.

Docker использует несколько типов namespace:

PID — изоляция идентификаторов процессов

NET — изоляция сетевых интерфейсов

MNT — изоляция точек монтирования файловой системы

IPC — изоляция межпроцессного взаимодействия

UTS — изоляция hostname и domain name

USER — изоляция пользователей и групп

Вместе с cgroups (которые ограничивают CPU, память и другие ресурсы) namespaces обеспечивают основу изоляции контейнеров.

**8. What do you know about the life cycle of a Docker container?**

The Docker container lifecycle describes the different states a container goes through from creation to removal.

Main stages:

Created – The container is created from an image but not started yet.

Running – The container is actively executing its main process.

Paused – The container processes are temporarily suspended.

Stopped (Exited) – The main process has stopped, but the container still exists.

Restarted – The container is stopped and started again (manually or via restart policy).

Removed (Deleted) – The container is permanently deleted from the system.

Typical flow: docker create → docker start → docker stop → docker rm.

The container runs as long as its main process (PID 1) is running. If that process stops or crashes, the container stops.

Жизненный цикл Docker-контейнера описывает состояния, через которые он проходит от создания до удаления.

Основные этапы:

Created – контейнер создан из образа, но ещё не запущен.

Running – контейнер выполняет основной процесс.

Paused – выполнение процессов временно приостановлено.

Stopped (Exited) – основной процесс завершён, но контейнер всё ещё существует.

Restarted – контейнер перезапускается вручную или по restart policy.

Removed – контейнер полностью удалён из системы.

Типичный поток: docker create → docker start → docker stop → docker rm.

Контейнер работает, пока работает его основной процесс (PID 1). Если этот процесс завершается или падает, контейнер останавливается.

**9. How would you check Docker Server or Client version?**

To check the Docker Client and Server (Daemon) versions, use the command: `docker version`

This command shows both:

- Client version

- Server (Engine) version

It also displays API version, Go version, Git commit, and build information.

If you only need the Docker Engine version, you can use: `docker --version`

To get detailed system information (including Docker Server details): `docker info`

Чтобы проверить версию Docker Client и Server (Daemon), используйте команду: `docker version`

Она показывает:

- версию клиента

- версию сервера (Docker Engine)

Также отображаются API version, Go version и информация о сборке.

Если нужна только версия Docker Engine, используйте: `docker --version`

Для получения подробной информации о системе и сервере Docker: `docker info`

**10. Is it possible to autoscale Docker Swarm?**

---

Yes, Docker Swarm supports scaling services, but autoscaling is not built-in by default. You can manually scale a service using: `docker service scale service_name=replicas` For automatic scaling, you need external tools or scripts that monitor metrics (CPU, memory, requests) and adjust replicas accordingly. In cloud environments (AWS, Azure, GCP), autoscaling can also be implemented at the infrastructure level using auto-scaling groups.
So, Docker Swarm supports scaling, but autoscaling requires additional tooling or integration.

Да, Docker Swarm поддерживает масштабирование сервисов, но автоматическое масштабирование не встроено по умолчанию. Масштабирование вручную выполняется командой: `docker service scale service_name=replicas` Для автоскейлинга нужны внешние инструменты или скрипты, которые мониторят метрики (CPU, память, нагрузку) и изменяют количество реплик. В облачных средах (AWS, Azure, GCP) автоскейлинг также можно реализовать на уровне инфраструктуры через auto-scaling группы. Таким образом, Docker Swarm поддерживает масштабирование, но автоскейлинг требует дополнительной настройки.

**11. How is orchestration managed in Docker?**

---

In Docker, orchestration is managed using Docker Swarm.

Docker Swarm is Docker’s native clustering and orchestration tool that allows you to manage multiple Docker hosts as a single cluster.

It uses a manager–worker architecture:

- Manager nodes handle cluster state, scheduling, and service orchestration.

- Worker nodes run the containers (tasks).

Orchestration in Swarm includes:

- Service deployment and scaling

- Load balancing (built-in routing mesh)

- Rolling updates and rollbacks

- Health checks and self-healing

- High availability

You define the desired state (number of replicas, image, network, etc.), and Swarm ensures the actual state matches it.

В Docker оркестрация управляется с помощью Docker Swarm. Docker Swarm — это встроенный инструмент кластеризации и оркестрации, который позволяет объединить несколько Docker-хостов в один кластер.

Он использует архитектуру manager–worker:

- Manager-ноды управляют состоянием кластера, планированием и оркестрацией сервисов.

- Worker-ноды запускают контейнеры (tasks).

Оркестрация включает:

- деплой и масштабирование сервисов

- встроенный load balancing (routing mesh)

- rolling updates и rollback

- health checks и self-healing

- высокую доступность

Вы задаёте желаемое состояние (количество реплик, образ, сеть и т.д.), а Swarm поддерживает фактическое состояние в соответствии с ним.

**12. What is container isolation and how is it achieved?**

---

Container isolation is the separation of containers from each other and from the host system to ensure security, stability, and resource control.
It ensures that processes inside one container cannot directly access or interfere with processes, filesystem, or network of another container.

Isolation is achieved using Linux kernel features:

- Namespaces – isolate system resources (PID, NET, MNT, IPC, UTS, USER).

- cgroups (Control Groups) – limit and manage resources like CPU, memory, and I/O.

- Union file systems – provide isolated layered filesystems for each container.

- Capabilities and seccomp – restrict available system calls and privileges.

Together, these mechanisms create lightweight isolation without the overhead of full virtual machines.

Изоляция контейнеров — это отделение контейнеров друг от друга и от хост-системы для обеспечения безопасности, стабильности и контроля ресурсов.
Она гарантирует, что процессы одного контейнера не могут напрямую вмешиваться в процессы, файловую систему или сеть другого контейнера.

Изоляция достигается с помощью механизмов ядра Linux:

- Namespaces — изолируют системные ресурсы (PID, NET, MNT, IPC, UTS, USER).

- cgroups — ограничивают и управляют ресурсами (CPU, память, I/O).

- Union file system — обеспечивает изолированную слоистую файловую систему.

- Capabilities и seccomp — ограничивают системные вызовы и привилегии.

Вместе эти механизмы обеспечивают лёгкую изоляцию без накладных расходов виртуальных машин.

**13. Why use cgroups in Docker?**

---

cgroups (Control Groups) are used in Docker to limit, prioritize, and monitor resource usage of containers.

They ensure that one container cannot consume all system resources and affect other containers or the host.

With cgroups, Docker can control:

- CPU usage (limits and shares)

- Memory limits (RAM and swap)

- Disk I/O limits

- Network bandwidth (indirectly via traffic control)

- Process count limits

cgroups provide resource isolation and stability, making containers predictable and preventing resource exhaustion.

cgroups (Control Groups) используются в Docker для ограничения, приоритизации и мониторинга использования ресурсов контейнерами.

Они гарантируют, что один контейнер не сможет занять все ресурсы системы и повлиять на другие контейнеры или хост.

С помощью cgroups Docker управляет:

- использованием CPU (лимиты и приоритеты)

- ограничениями памяти (RAM и swap)

- ограничениями дискового I/O

- сетевой пропускной способностью (косвенно)

- количеством процессов

cgroups обеспечивают контроль ресурсов и стабильность системы, предотвращая их истощение.

**14. What do you understand by Docker security scan?**

---

Docker security scan is the process of analyzing Docker images to detect security vulnerabilities, outdated packages, and misconfigurations. It scans image layers and dependencies for known CVEs (Common Vulnerabilities and Exposures) and provides a report with severity levels. Docker provides built-in scanning via docker scan (powered by Snyk), and you can also use external tools like Trivy, Clair, or Anchore. Security scanning helps identify risks before deploying containers to production and supports DevSecOps practices.

Docker security scan — это процесс анализа Docker-образов для выявления уязвимостей, устаревших пакетов и неправильных настроек. Он проверяет слои образа и зависимости на наличие известных CVE (Common Vulnerabilities and Exposures) и формирует отчёт с уровнями критичности. В Docker есть встроенная команда docker scan (на базе Snyk), а также можно использовать внешние инструменты: Trivy, Clair, Anchore. Сканирование безопасности помогает обнаружить риски до деплоя в production и поддерживает практики DevSecOps.

**15. What are Docker Plugins?**

---

Docker plugins are extensions that add additional functionality to Docker without modifying its core. They allow Docker to integrate with external systems and services such as storage providers and networking solutions.
There are two main types of Docker plugins:

- Volume plugins – enable integration with external storage systems (e.g., NFS, cloud storage, distributed storage).

- Network plugins – provide custom networking solutions beyond the default Docker networking drivers.

Plugins run in isolated environments and communicate with Docker through a defined API.

Docker plugins — это расширения, которые добавляют дополнительную функциональность без изменения ядра Docker.
Они позволяют интегрировать Docker с внешними системами и сервисами, например хранилиищами и сетевыми решениями.

Существует два основных типа плагинов:

- Volume plugins — интеграция с внешними системами хранения данных (NFS, облачные хранилища, распределённые системы).

- Network plugins — реализация кастомных сетевых решений помимо стандартных драйверов Docker.

Плагины работают в изолированной среде и взаимодействуют с Docker через определённый API.

**16. What is the difference between Docker and Kubernetes?**

---

Docker is a containerization platform used to build, package, and run containers.

Kubernetes is a container orchestration system used to manage, scale, and automate containerized applications across clusters.

Key differences:

Purpose:
Docker creates and runs containers.
Kubernetes manages and orchestrates containers at scale.

Scope:
Docker works mainly on a single host (or Swarm cluster).
Kubernetes manages multi-node clusters.

Scaling:
Docker supports manual scaling (or limited orchestration via Swarm).
Kubernetes provides advanced auto-scaling, self-healing, rolling updates, and service discovery.

Architecture:
Docker focuses on container runtime and image management.
Kubernetes focuses on cluster management and desired state reconciliation.

In short: Docker runs containers, Kubernetes orchestrates them.

Docker — это платформа контейнеризации для сборки и запуска контейнеров.

Kubernetes — это система оркестрации контейнеров для управления, масштабирования и автоматизации контейнеризированных приложений в кластере.

Основные различия:

Назначение:

- Docker создаёт и запускает контейнеры.
- Kubernetes управляет контейнерами и масштабирует их.

Масштаб:

- Docker обычно работает на одном хосте (или в Swarm-кластере).
- Kubernetes управляет множеством нод в кластере.

Масштабирование:

- Docker поддерживает ручное масштабирование.
- Kubernetes предоставляет автоскейлинг, self-healing, rolling updates и service discovery.

Архитектура:

- Docker — это runtime и управление образами.
- Kubernetes — это управление кластером и поддержание желаемого состояния.

Кратко: Docker запускает контейнеры, Kubernetes ими управляет.

**17. How are Kubernetes and Docker Swarm different?**

---

Kubernetes and Docker Swarm are both container orchestration tools, but they differ in complexity, features, and scalability.

1. Complexity
   Docker Swarm is simpler to set up and easier to use.
   Kubernetes has a steeper learning curve and more complex architecture.

2. Installation & Setup
   Swarm is built into Docker and can be enabled with a single command (docker swarm init).
   Kubernetes requires separate installation and cluster setup.

3. Scaling & Features
   Kubernetes provides advanced features like auto-scaling, self-healing, rolling updates, service discovery, and declarative configuration.
   Swarm supports scaling and rolling updates but has fewer advanced orchestration features.

4. Architecture
   Swarm uses a simple manager–worker model.
   Kubernetes uses a master/control plane and worker nodes with multiple internal components (API server, scheduler, controller manager, etc.).

5. Ecosystem
   Kubernetes has a large ecosystem and strong community support.
   Swarm has a smaller ecosystem and is less commonly used in large-scale production environments.

In short: Swarm is simpler and lightweight; Kubernetes is more powerful and production-ready at scale.

Kubernetes и Docker Swarm — это инструменты оркестрации контейнеров, но они отличаются по сложности, возможностям и масштабируемости.

1. Сложность
   Docker Swarm проще в настройке и использовании.
   Kubernetes имеет более сложную архитектуру и высокий порог входа.

2. Установка
   Swarm встроен в Docker и включается одной командой (docker swarm init).
   Kubernetes требует отдельной установки и настройки кластера.

3. Масштабирование и возможности
   Kubernetes поддерживает автоскейлинг, self-healing, rolling updates, service discovery и декларативную конфигурацию.
   Swarm поддерживает масштабирование и rolling updates, но функциональность ограничена.

4. Архитектура
   Swarm использует модель manager–worker.
   Kubernetes использует control plane и worker-ноды с несколькими компонентами.

5. Экосистема
   Kubernetes имеет более развитую экосистему и широкую поддержку сообщества.
   Swarm используется реже в крупных production-системах.

Кратко: Swarm проще, Kubernetes мощнее и лучше подходит для масштабных production-сред.

**18. Kubernetes vs. Docker: which one is best for containerization?**

---

Docker is best for containerization itself, while Kubernetes is best for orchestrating containers at scale. Docker is responsible for building images and running containers. It provides the container runtime and packaging mechanism. Kubernetes does not replace containerization — it manages and orchestrates containers across multiple nodes.

So the choice depends on the use case:

- For simple applications or local development → Docker alone is enough.

- For large-scale, distributed, production systems → Kubernetes is better.

In practice, they are complementary, not competitors: Docker (or another container runtime) handles containerization, and Kubernetes handles orchestration.

Docker лучше подходит именно для контейнеризации — сборки и запуска контейнеров. Kubernetes предназначен не для создания контейнеров, а для их оркестрации и управления в кластере.

Выбор зависит от задачи:

- Для небольших проектов или локальной разработки достаточно Docker.

- Для масштабируемых production-систем лучше использовать Kubernetes.

На практике они не конкуренты, а дополняют друг друга: Docker занимается контейнерами, Kubernetes — их управлением и масштабированием.

**19. What do you understand about Pod in Kubernetes?**

---

A Pod is the smallest deployable unit in Kubernetes.

It represents one or more tightly coupled containers that share the same network namespace and storage volumes.

Containers inside a Pod:

- Share the same IP address and port space

- Can communicate via localhost

- Share mounted volumes

Typically, a Pod runs a single main container, but it can also include sidecar containers (e.g., for logging or monitoring).

Pods are ephemeral — if a Pod fails, Kubernetes replaces it automatically (usually via a Deployment or ReplicaSet).

Pod — это минимальная единица деплоя в Kubernetes.

Он представляет собой один или несколько тесно связанных контейнеров, которые работают вместе.

Контейнеры внутри Pod:

- Имеют общий IP-адрес и сетевое пространство

- Могут общаться через localhost

- Могут использовать общие тома (volumes)

Обычно Pod содержит один основной контейнер, но может включать дополнительные (sidecar) контейнеры.

Pod является временной сущностью — если он падает, Kubernetes автоматически создаёт новый (через Deployment или ReplicaSet).

**20. How to manage sensitive data in Kubernetes and Docker?**

---

ensitive data (passwords, API keys, certificates) should never be hardcoded into images or stored in plain environment variables inside Dockerfiles.

In Docker

- Use Docker Secrets (in Swarm mode) to securely store and inject secrets into containers.

- Mount secrets as files instead of passing them as plain environment variables.

- Use external secret managers (Vault, AWS Secrets Manager, etc.).

- Avoid committing .env files with real credentials to version control.

In Kubernetes

- Use Secrets objects to store sensitive data (base64-encoded).

- Mount Secrets as environment variables or files inside Pods.

- Enable encryption at rest in etcd.

- Use RBAC to restrict access to Secrets.

- Integrate with external secret managers (HashiCorp Vault, cloud providers).

Best practice: follow the principle of least privilege and separate configuration from code.

Конфиденциальные данные (пароли, API-ключи, сертификаты) нельзя хардкодить в образы или хранить в Dockerfile.

В Docker

- Использовать Docker Secrets (в режиме Swarm).

- Передавать секреты через файлы, а не обычные переменные окружения.

- Использовать внешние менеджеры секретов (Vault, AWS Secrets Manager и др.).

- Не коммитить реальные .env файлы в репозиторий.

В Kubernetes

- Использовать объекты Secrets для хранения чувствительных данных.

- Монтировать Secrets как переменные окружения или файлы в Pod.

- Включить encryption at rest для etcd.

- Ограничивать доступ через RBAC.

- Интегрироваться с внешними менеджерами секретов.

Лучшие практики: принцип наименьших привилегий и разделение конфигурации и кода.

**21. How would you use Jenkins to push a Docker container image to the Docker Hub?**

---

To push a Docker image to Docker Hub using Jenkins, you typically configure a CI pipeline that builds the image, authenticates to Docker Hub, and pushes the image.

Steps:

1. Install required tools
   - Jenkins

   - Docker installed on the Jenkins agent

   - Docker Pipeline plugin (if using Jenkins Pipeline)

2. Store Docker Hub credentials
   - Add Docker Hub username/password (or access token) in Jenkins Credentials Manager.

3. Create a Jenkins Pipeline

Example Jenkinsfile:

```
pipeline {
agent any

    environment {
        IMAGE_NAME = "your_dockerhub_username/app-name"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}:latest")
                }
            }
        }

        stage('Login to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh "echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin"
                }
            }
        }

        stage('Push Image') {
            steps {
                sh "docker push ${IMAGE_NAME}:latest"
            }
        }
    }

}
```

Process explanation:

- Jenkins checks out the source code.

- Builds the Docker image using Dockerfile.

- Logs in to Docker Hub using stored credentials.

- Pushes the image to Docker Hub repository.

Best practice:

- Use Docker Hub access tokens instead of passwords.

- Tag images with version numbers or build IDs.

- Run Jenkins agents in Docker or Kubernetes for better isolation.

Чтобы запушить Docker-образ в Docker Hub через Jenkins, нужно настроить CI-пайплайн, который собирает образ, авторизуется и отправляет его в репозиторий.

Шаги:

- Установить Jenkins и Docker на агенте.

- Добавить учетные данные Docker Hub в Jenkins Credentials.

- Создать Jenkins Pipeline.

В Jenkinsfile:

- Код забирается из репозитория.

- Собирается Docker image.

- Выполняется логин в Docker Hub.

- Образ пушится в репозиторий.

Рекомендуется:

- Использовать access token вместо пароля.

- Версионировать теги (не только latest).

Изолировать агенты Jenkins (Docker/Kubernetes).

**22. What would you do if you have to use Docker in multiple application environments?**

---

If I need to use Docker across multiple environments (dev/stage/prod), I focus on consistency, configuration separation, and reproducible builds.

- Build one immutable image and promote the same image through environments (don’t rebuild per env).

- Use environment-specific configuration via environment variables, .env files, or mounted config (never bake secrets into the image).

- Use separate compose files / overrides (e.g., docker-compose.yml + docker-compose.prod.yml) for differences like replicas, ports, volumes, logging.

- Use different resources and endpoints per environment (DBs, caches, external APIs) and isolate networks.

- Use tagging strategy (version/build number) and a registry (Docker Hub/private) to control deployments.

- Apply security + limits: least-privilege, non-root user, read-only FS where possible, healthchecks, CPU/memory limits.

- Automate with CI/CD to build once, scan, push, and deploy with the right config.

Если нужно использовать Docker в нескольких окружениях (dev/stage/prod), я делаю упор на одинаковость среды, разделение конфигурации и воспроизводимые сборки.

- Собираю один неизменяемый образ и продвигаю один и тот же image по окружениям (не пересобираю под каждое env).

- Выношу конфигурацию по окружениям во внешние параметры: env vars, .env, монтируемые конфиги (секреты не вшиваю в образ).

- Использую несколько compose-файлов/override (например, docker-compose.yml + docker-compose.prod.yml) для различий: реплики, порты, volume, логирование.

- Разделяю ресурсы и интеграции по окружениям (разные БД/кэши/API), изолирую сети.

- Применяю стратегию тегов (версия/номер билда) и registry (Docker Hub/private) для контролируемых деплоев.

- Добавляю безопасность и лимиты: non-root, least privilege, healthcheck, ограничения CPU/RAM, по возможности read-only FS.

- Автоматизирую через CI/CD: build once → scan → push → deploy с нужной конфигурацией.

**23. Explain what the Docker Registry is and what it does**

---

Docker Registry is a service that stores and distributes Docker images. It acts as a central repository where images are pushed (uploaded) and pulled (downloaded) by Docker clients. When you run docker push, the image is uploaded to a registry. When you run docker pull, the image is downloaded from a registry.

There are two main types of registries:

- Public registry (e.g., Docker Hub)

- Private registry (self-hosted or cloud-based)

The registry manages:

- Image storage

- Versioning through tags

- Access control and authentication

- Image distribution across environments

In short, Docker Registry enables sharing and managing container images across teams and environments.

Docker Registry — это сервис для хранения и распространения Docker-образов. Он выступает как центральное хранилище, куда образы загружаются (docker push) и откуда скачиваются (docker pull).

Существует два типа registry:

- Публичный (например, Docker Hub)

- Приватный (self-hosted или облачный)

Registry отвечает за:

- Хранение образов

- Версионирование через теги

- Аутентификацию и контроль доступа

- Распространение образов между окружениями

Проще говоря, Docker Registry позволяет централизованно хранить и распространять контейнерные образы.

**24. What is meant by the Docker Container lifecycle?**

---

The Docker container lifecycle refers to the different states a container goes through from creation to deletion.

Main stages of the lifecycle:

1. Created – The container is created from an image but not started yet.

2. Running – The container is actively executing its main process.

3. Paused – The container’s processes are temporarily suspended.

4. Stopped (Exited) – The main process has finished or crashed, but the container still exists.

5. Restarted – The container is started again manually or via a restart policy.

6. Removed – The container is permanently deleted from the system.

The container runs as long as its main process (PID 1) is running. if that process stops, the container stops.

Typical flow: docker create → docker start → docker stop → docker rm

Жизненный цикл Docker-контейнера — это набор состояний, через которые контейнер проходит от создания до удаления.

Основные этапы:

1. Created – контейнер создан, но ещё не запущен.

2. Running – контейнер выполняет основной процесс.

3. Paused – выполнение процессов временно приостановлено.

4. Stopped (Exited) – основной процесс завершён, но контейнер всё ещё существует.

5. Restarted – контейнер перезапускается вручную или по политике перезапуска.

6. Removed – контейнер полностью удалён из системы.

Контейнер работает, пока работает его основной процесс (PID 1). Если процесс завершается — контейнер останавливается.

**25. Outline the main stages of the Docker Container lifecycle.**

---

The main stages of the Docker container lifecycle are:

- Created - The container is created from an image but has not started yet.

- Running - The container is executing its main process (PID 1).

- Paused - The container processes are temporarily suspended.

- Stopped (Exited) - The main process has completed or failed, but the container still exists.

- Restarted - The container is stopped and started again (manually or via restart policy).

- Removed - The container is permanently deleted from the system.

Typical flow: create → start → running → stop → remove

Основные стадии жизненного цикла Docker-контейнера:

- Created -Контейнер создан из образа, но ещё не запущен.

- Running - Контейнер выполняет основной процесс.

- Paused - Процессы контейнера временно приостановлены.

- Stopped (Exited) - Основной процесс завершён, но контейнер всё ещё существует.

- Restarted - Контейнер перезапущен вручную или по restart policy.

- Removed - Контейнер полностью удалён из системы.

Типичный поток: create → start → running → stop → remove

**26. Name and describe the crucial Docker commands**

---

Here are the crucial Docker commands and their purpose:

- docker build - Builds a Docker image from a Dockerfile.

- docker pull - Downloads an image from a Docker registry.

- docker push - Uploads an image to a Docker registry.

- docker run - Creates and starts a new container from an image.

- docker start - Starts an existing stopped container.

- docker stop - Gracefully stops a running container.

- docker restart - Stops and then starts a container.

- docker ps - Lists running containers (-a shows all containers).

- docker images - Lists locally available Docker images.

- docker logs - Displays logs from a container.

- docker exec - Runs a command inside a running container.

- docker rm - Removes a stopped container.

- docker rmi - Removes a Docker image.

- docker inspect - Shows detailed information about a container or image.

Основные команды Docker:

- docker build — сборка образа из Dockerfile.

- docker pull — загрузка образа из registry.

- docker push — отправка образа в registry.

- docker run — создание и запуск контейнера.

- docker start — запуск остановленного контейнера.

- docker stop — корректная остановка контейнера.

- docker restart — перезапуск контейнера.

- docker ps — список контейнеров (-a — все).

- docker images — список локальных образов.

- docker logs — просмотр логов контейнера.

- docker exec — выполнение команды внутри контейнера.

- docker rm — удаление контейнера.

- docker rmi — удаление образа.

- docker inspect — детальная информация об объекте Docker.

**27. Explain what a namespace is in Docker**

---

A namespace in Docker is a Linux kernel feature that provides isolation between containers. Namespaces ensure that each container has its own separate view of system resources, so processes inside one container cannot see or interfere with others.

Docker uses several types of namespaces:

- PID namespace – isolates process IDs (each container has its own process tree).

- NET namespace – isolates network interfaces, IP addresses, and routing tables.

- MNT namespace – isolates filesystem mount points.

- IPC namespace – isolates inter-process communication mechanisms.

- UTS namespace – isolates hostname and domain name.

- USER namespace – isolates user and group IDs.

Namespaces provide logical separation of system resources, and together with cgroups (resource limits), they form the foundation of container isolation.

Namespace в Docker — это механизм ядра Linux, обеспечивающий изоляцию контейнеров. Он позволяет каждому контейнеру иметь собственное представление системных ресурсов, поэтому процессы одного контейнера не видят процессы другого.

Docker использует несколько типов namespace:

- PID — изоляция процессов.

- NET — изоляция сети.

- MNT — изоляция точек монтирования.

- IPC — изоляция межпроцессного взаимодействия.

- UTS — изоляция имени хоста.

- USER — изоляция пользователей и групп.

Namespace обеспечивает логическую изоляцию ресурсов, а вместе с cgroups формирует основу безопасности контейнеров.

**28. Explain what the Docker Swarm tool is.**

---

Docker Swarm is Docker’s native container orchestration tool used to manage a cluster of Docker hosts.

It allows multiple Docker nodes to work together as a single virtual system.

Swarm uses a manager–worker architecture:

- Manager nodes manage the cluster state, scheduling, and orchestration.

- Worker nodes run the containers (tasks).

Key features of Docker Swarm:

- Service deployment and scaling

- Load balancing (routing mesh)

- Rolling updates and rollbacks

- Self-healing (restarting failed containers)

- High availability

You define the desired state (number of replicas, image, network), and Swarm ensures the cluster maintains that state.

Docker Swarm — это встроенный инструмент оркестрации контейнеров в Docker, предназначенный для управления кластером хостов.

Он объединяет несколько Docker-нoд в одну логическую систему.

Swarm использует архитектуру manager–worker:

- Manager-ноды управляют состоянием кластера и планированием.

- Worker-ноды запускают контейнеры.

Основные возможности:

- Деплой и масштабирование сервисов

- Балансировка нагрузки

- Rolling updates и rollback

- Автоматический перезапуск контейнеров

- Высокая доступность

Вы задаёте желаемое состояние, а Swarm поддерживает его в кластере.

**29. Explain what the Docker Swarm tool does**

---

Docker Swarm is a native Docker tool that provides container orchestration across multiple Docker hosts. It turns a group of Docker nodes into a single cluster and manages containers as services instead of individual instances.

Docker Swarm performs the following functions:

- Cluster management – joins multiple nodes into one logical system.

- Service orchestration – deploys and maintains services with a defined number of replicas.

- Load balancing – distributes traffic across service replicas using the routing mesh.

- Scaling – increases or decreases the number of container replicas.

- Self-healing – automatically restarts failed containers.

- Rolling updates and rollbacks – updates services with minimal downtime.

In short, Docker Swarm automates the deployment, scaling, and management of containerized applications in a cluster.

Docker Swarm — это встроенный инструмент оркестрации Docker для управления контейнерами в кластере. Он объединяет несколько Docker-хостов в одну систему и управляет контейнерами как сервисами.

Docker Swarm выполняет:

- Управление кластером — объединяет ноды в один кластер.

- Оркестрацию сервисов — деплоит и поддерживает заданное количество реплик.

- Балансировку нагрузки — распределяет трафик между контейнерами.

- Масштабирование — увеличивает или уменьшает число реплик.

- Self-healing — автоматически перезапускает упавшие контейнеры.

- Rolling updates и rollback — обновляет сервисы без простоя.

Проще говоря, Swarm автоматизирует деплой, масштабирование и управление контейнерными приложениями.

**30. Outline the main functionalities of Docker**

---

The main functionalities of Docker are:

- Containerization - Packages applications and their dependencies into lightweight, portable containers.

- Image Management - Builds, stores, tags, and distributes images via registries.

- Container Lifecycle Management - Creates, runs, stops, restarts, and removes containers.

- Networking - Provides container networking, port mapping, service discovery, and isolated networks.

- Storage Management - Manages volumes and bind mounts for persistent data.

- Resource Isolation and Limiting - Uses namespaces and cgroups to isolate containers and control CPU, memory, and I/O usage.

- Orchestration (with Swarm) - Deploys and manages multi-container applications across clusters.

- Security Features - Supports secrets management, user namespaces, capabilities, and image scanning.

Основные функции Docker:

- Контейнеризация - Упаковка приложения и зависимостей в изолированный контейнер.

- Управление образами - Сборка, хранение, тегирование и распространение образов.

- Управление жизненным циклом контейнеров - Создание, запуск, остановка и удаление контейнеров.

- Сетевые возможности - Настройка сетей, проброс портов и изоляция сетевого трафика.

- Работа с хранилищем - Использование volume и bind mount для постоянных данных.

- Изоляция и ограничение ресурсов - Контроль CPU, памяти и других ресурсов через namespaces и cgroups.

- Оркестрация (через Swarm) - Управление сервисами и масштабирование в кластере.

- Безопасность - Поддержка секретов, ограничений привилегий и сканирования образов.

**31. Explain what Docker objects are.**

---

Docker objects are the core components that Docker uses to build, run, and manage containerized applications.

The main Docker objects are:

- Images - Read-only templates used to create containers. They contain the application code, runtime, libraries, and dependencies.

- Containers - Runnable instances of images. They are isolated environments where applications execute.

- Volumes - Persistent storage mechanisms used to store data outside the container’s writable layer.

- Networks - Enable communication between containers and with the outside world.

- Plugins - Extensions that add functionality such as custom storage or networking drivers.

These objects work together to support containerization, deployment, networking, and data persistence.

Docker objects — это основные сущности, которые Docker использует для создания и управления контейнеризированными приложениями.

Основные объекты Docker:

- Images (образы) - Неизменяемые шаблоны для создания контейнеров.

- Containers (контейнеры) - Запущенные экземпляры образов.

- Volumes (тома) - Механизм постоянного хранения данных вне контейнера.

- Networks (сети) - Обеспечивают взаимодействие между контейнерами и внешним миром.

- Plugins (плагины) - Расширяют функциональность Docker.

Эти объекты вместе обеспечивают контейнеризацию, хранение данных, сетевое взаимодействие и управление приложениями.

**32. Should you use stateful or stateless applications for Docker containers? Why?**

---

Stateless applications are generally preferred for Docker containers. Stateless containers do not store data inside the container itself. All state (sessions, files, database data) is stored externally — for example, in a database, cache, or persistent volume.

Why stateless is better:

- Easier horizontal scaling (add/remove containers freely)

- Better fault tolerance (if a container dies, no data is lost)

- Simpler orchestration and load balancing

- Faster deployments and rollbacks

Stateful applications can run in Docker, but they require persistent storage (volumes) and careful data management. They are more complex to scale and manage.
Best practice: keep containers stateless and externalize state to dedicated storage systems.

Для Docker-контейнеров предпочтительнее использовать stateless-приложения.

Stateless означает, что контейнер не хранит состояние внутри себя. Все данные (сессии, файлы, БД) находятся во внешних сервисах или persistent volume.

Почему stateless лучше:

- Легче масштабировать горизонтально

- Нет потери данных при падении контейнера

- Проще балансировка нагрузки

- Быстрее деплой и rollback

Stateful-приложения можно запускать в Docker, но требуется использование volume и более сложное управление данными. Лучшая практика — делать контейнеры stateless, а состояние хранить во внешних системах.

**33. What are the main tasks that developers can automate with container orchestration?**

---

Container orchestration automates the deployment, management, and scaling of containerized applications.

The main tasks developers can automate are:

- Container Deployment - Automatically deploy containers across multiple nodes.

- Scaling - Increase or decrease the number of container replicas based on demand.

- Load Balancing - Distribute traffic across running containers.

- Self-Healing - Automatically restart failed containers or reschedule them on healthy nodes.

- Rolling Updates and Rollbacks - Update applications with minimal downtime and revert if something fails.

- Service Discovery - Automatically register and locate services inside the cluster.

- Resource Management - Allocate and limit CPU, memory, and other resources.

- Configuration and Secret Management - Inject environment variables, configs, and secrets securely.

- Health Monitoring - Monitor container health and take corrective actions.

In short, orchestration automates operations tasks and ensures high availability, scalability, and reliability.

Оркестрация контейнеров автоматизирует развертывание, управление и масштабирование приложений.

Основные задачи, которые можно автоматизировать:

- Деплой контейнеров - Автоматическое размещение контейнеров на нодах кластера.

- Масштабирование - Увеличение или уменьшение количества реплик.

- Балансировка нагрузки - Распределение трафика между контейнерами.

- Self-healing - Автоматический перезапуск упавших контейнеров.

- Rolling updates и rollback - Обновления без простоя и возможность отката.

- Service discovery - Автоматическое обнаружение сервисов.

- Управление ресурсами - Ограничение CPU, памяти и других ресурсов.

- Управление конфигурацией и секретами - Безопасная передача настроек и паролей.

- Мониторинг здоровья - Проверка состояния контейнеров и автоматическая реакция.

Кратко: оркестрация автоматизирует эксплуатационные задачи и обеспечивает масштабируемость и отказоустойчивость.

**34. How would you scale Docker containers?**

---

You can scale Docker containers by increasing the number of container instances (replicas). How you do it depends on whether you use plain Docker, Compose, or an orchestrator.

1. Docker Compose (most common) Scale a service to N replicas: `docker compose up -d --scale api=3` This runs 3 containers for the api service (works best when the service is stateless).

2. Docker Swarm (orchestration) Scale a Swarm service: `docker service scale api=3` Swarm distributes replicas across nodes and provides built-in load balancing.

3. Plain Docker (no orchestration) You manually run multiple containers: `docker run -d --name api-1 myapp` `docker run -d --name api-2 myapp` Then you need a load balancer (e.g., Nginx/Traefik) because Docker alone won’t automatically route traffic across replicas.

Key considerations:

- Prefer stateless containers

- Externalize state (DB/Redis/volumes)

- Use a load balancer and health checks

Масштабирование Docker-контейнеров — это увеличение количества экземпляров (реплик). Способ зависит от того, используешь ли ты Docker, Compose или оркестратор.

1. Docker Compose Запуск N реплик сервиса: `docker compose up -d --scale api=3` (лучше работает для stateless-сервисов)

2. Docker Swarm Масштабирование сервиса в кластере: `docker service scale api=3` Swarm распределит реплики по нодам и даст встроенную балансировку.

3. Обычный Docker (без оркестрации) Запускаешь несколько контейнеров вручную: `docker run -d --name api-1 myapp` `docker run -d --name api-2 myapp`
   И нужен балансировщик (Nginx/Traefik), потому что Docker сам трафик по репликам не распределит.

Важно:

- Делать сервисы stateless

- Состояние хранить во внешних системах (DB/Redis/volumes)

- Использовать балансировку и health checks

**35. Which solution would you use to manage and store Docker images?**

---

To manage and store Docker images, I would use a container registry.

Common solutions:

- Docker Hub — public registry and simple private repos; good for quick sharing and small/medium projects.

- Cloud registries — AWS ECR, Google Artifact Registry / GCR, Azure Container Registry (ACR); best for production because they integrate with IAM, networking, and CI/CD.

- Self-hosted/private registries — Harbor, JFrog Artifactory, Nexus Registry, or the official Docker Registry; good when you need full control, on-prem, policies, and compliance.

What I look for when choosing:

- Access control (RBAC/IAM), private repos

- Image signing/scanning, vulnerability reports

- Replication, retention policies, cleanup

- Integration with CI/CD and Kubernetes

Для хранения и управления Docker-образами я бы использовал container registry.

Варианты:

- Docker Hub — удобно и быстро, подходит для простых кейсов и небольших проектов.

- Облачные registry — AWS ECR, GCP Artifact Registry / GCR, Azure ACR; чаще лучший выбор для production из-за интеграции с IAM и CI/CD.

- Self-hosted/private registry — Harbor, JFrog Artifactory, Nexus Registry или официальный Docker Registry; когда нужен полный контроль, on-prem и комплаенс.

Критерии выбора:

- Контроль доступа (RBAC/IAM)

- Сканирование уязвимостей/подпись образов

- Retention/cleanup политики, репликация

- Интеграция с CI/CD и Kubernetes

**36. How would you create containers from an image?**

---

You create containers from an image using the docker run command.

The command pulls the image (if it is not available locally), creates a container from it, and starts it.

Example: `docker run nginx`

This will create and start a container from the nginx image.

Common options:

    -d — run container in detached (background) mode

    -p — map host port to container port

    --name — assign a name to the container

    -v — mount volumes

Example with options: `docker run -d -p 8080:80 --name my-nginx nginx`

This command:

- Creates a container from the nginx image

- Runs it in the background

- Maps port 8080 (host) to 80 (container)

- Names the container my-nginx

You can also create a container without starting it using: `docker create image_name`

and then start it later with: `docker start container_name.`

Контейнер из образа создаётся с помощью команды docker run.

Эта команда:

- при необходимости скачивает образ

- создаёт контейнер

- запускает его

Пример: `docker run nginx`

Часто используемые параметры:

    -d — запуск в фоновом режиме

    -p — проброс портов

    --name — имя контейнера

    -v — подключение томов

Пример: `docker run -d -p 8080:80 --name my-nginx nginx`

Команда создаёт контейнер из образа nginx, запускает его в фоне и пробрасывает порт.

Также можно создать контейнер без запуска: `docker create image_name`

А затем запустить его командой: `docker start container_name.`

**37. Talk about hypervisors and their functions.**

---

A hypervisor is software that allows multiple virtual machines (VMs) to run on a single physical host by virtualizing hardware resources.

It creates and manages isolated virtual environments where each VM runs its own operating system and applications.

Main functions of a hypervisor:

- Resource Allocation - Distributes CPU, memory, storage, and network resources among virtual machines.

- Isolation - Ensures that each virtual machine operates independently and cannot interfere with others.

- Virtual Hardware Management - Provides virtual CPUs, disks, network interfaces, and other hardware components to VMs.

- VM Lifecycle Management - Creates, starts, stops, pauses, and deletes virtual machines.

- Security and Stability - Protects the host system and other VMs from failures or attacks within a single VM.

Types of hypervisors:

- Type 1 (Bare-metal)
  Runs directly on hardware without a host OS.
  Examples: VMware ESXi, Microsoft Hyper-V, Xen.

- Type 2 (Hosted)
  Runs on top of an existing operating system.
  Examples: VirtualBox, VMware Workstation.

Hypervisors are used in cloud computing and data centers to efficiently utilize hardware and run multiple isolated environments.

Гипервизор — это программное обеспечение, которое позволяет запускать несколько виртуальных машин на одном физическом сервере.

Он виртуализирует аппаратные ресурсы и создаёт изолированные среды, где каждая виртуальная машина может работать со своей операционной системой.

Основные функции гипервизора:

- Распределение ресурсов - Управляет использованием CPU, памяти, диска и сети между виртуальными машинами.

- Изоляция - Обеспечивает независимую работу виртуальных машин.

- Виртуальное оборудование - Предоставляет виртуальные CPU, диски и сетевые интерфейсы.

- Управление жизненным циклом VM - Создание, запуск, остановка и удаление виртуальных машин.

- Безопасность и стабильность - Изолирует сбои и угрозы внутри отдельных VM.

Типы гипервизоров:

- Type 1 (bare-metal) — работают напрямую на железе (VMware ESXi, Hyper-V, Xen).

- Type 2 (hosted) — работают поверх обычной ОС (VirtualBox, VMware Workstation).

Гипервизоры широко используются в облаках и дата-центрах для эффективного использования ресурсов.

**38. How can you remove all stopped containers and unused networks in Docker?**

---

You can remove all stopped containers and unused networks using Docker prune commands.

Remove stopped containers `docker container prune`

This command deletes all containers that are in the stopped state.

Remove unused networks `docker network prune`

This removes networks that are not used by any containers.

**Remove everything unused at once**

You can clean up multiple unused resources with: `docker system prune`

This removes:

- stopped containers

- unused networks

- dangling images

- build cache

If you also want to remove unused images: `docker system prune -a`

Summary

- docker container prune → remove stopped containers

- docker network prune → remove unused networks

- docker system prune → clean multiple unused Docker resources

Удалить все остановленные контейнеры и неиспользуемые сети можно с помощью команд prune.

Удалить остановленные контейнеры: `docker container prune`

Удалить неиспользуемые сети: `docker network prune`

Удалить всё неиспользуемое: `docker system prune`

Эта команда очищает:

- остановленные контейнеры

- неиспользуемые сети

- dangling images

- build cache

Для удаления всех неиспользуемых образов: `docker system prune -a`

**39. When a container exists, is it possible for you to lose data?**

---

Yes, it is possible to lose data when a container exits if the data is stored inside the container’s writable layer.

Containers are ephemeral, meaning their internal filesystem can be removed when the container is deleted.

If the container stops or is removed, any data stored inside the container may be lost.

To prevent data loss, Docker provides persistent storage options:

- Volumes – the recommended way to persist data outside the container lifecycle.

- Bind mounts – map directories from the host into the container.

- External storage systems – databases, object storage, etc.

Best practice: store application state and important data outside the container.

Да, данные могут быть потеряны, если контейнер завершился и данные хранятся внутри контейнера.

Контейнеры являются временными (ephemeral), поэтому их файловая система может быть удалена вместе с контейнером.

Если контейнер остановить или удалить, данные внутри него могут исчезнуть.

Чтобы избежать потери данных, используются:

- Volumes — основной способ постоянного хранения данных.

- Bind mounts — подключение директорий хоста к контейнеру.

- Внешние системы хранения — базы данных, object storage и т.д.

Лучшая практика — хранить состояние и данные вне контейнера.

**40. Is there a limit on how many containers you can run in Docker?**

---

There is no fixed limit on the number of containers you can run in Docker.

The number of containers depends mainly on the available system resources such as CPU, memory, disk I/O, and network capacity.

Since containers share the host OS kernel, they are lightweight compared to virtual machines, so a single host can run many containers.

However, practical limits are determined by:

- Available CPU and RAM

- Storage performance and capacity

- Network bandwidth

- Operating system limits (e.g., number of processes, file descriptors)

In large-scale environments, container orchestration tools like Kubernetes or Docker Swarm are used to distribute containers across multiple nodes.

Жёсткого ограничения на количество контейнеров в Docker нет.

Практические ограничения определяются:

- ресурсами CPU и RAM

- производительностью диска

- сетью

- лимитами операционной системы (процессы, file descriptors)

В больших системах контейнеры распределяются по нескольким серверам с помощью оркестраторов, например Kubernetes или Docker Swarm.

**41. Differentiate between Container Logging and Daemon Logging.**

---

Container Logging and Daemon Logging refer to different levels of logging in Docker.

**Container logging** records the output generated by the application running inside a container.

- Captures stdout and stderr from the container process.

- Used to monitor application behavior and debug issues.

- Accessed using the command: `docker logs container_name`

- Can be managed using logging drivers (json-file, syslog, fluentd, etc.).

**Daemon logging** records logs produced by the Docker daemon (dockerd) itself.

- Tracks Docker engine activities such as container lifecycle events, API requests, and system errors.

- Useful for debugging Docker infrastructure issues.

- Logs are usually stored in system logs (e.g., /var/log/docker.log or via systemd journal).

Key Difference

- Container logging → logs from the application running inside the container.

- Daemon logging → logs from the Docker engine managing containers.

<br>

Container Logging и Daemon Logging относятся к разным уровням логирования в Docker.

**Container Logging** — это вывод приложения, которое работает внутри контейнера.

- Захватывает stdout и stderr процесса контейнера.

- Используется для мониторинга и отладки приложения.

- Просматривается командой: `docker logs container_name`

- Может использовать разные logging drivers.

**Daemon Logging** — это логи самого Docker Engine.

- Отражают работу Docker: создание контейнеров, API-запросы, ошибки системы.

- Используются для диагностики проблем инфраструктуры Docker.

- Обычно хранятся в системных логах.

Основное отличие

- Container logging — логи приложения внутри контейнера.

- Daemon logging — логи Docker Engine.

**42. Does Docker provide support for IPV6?**

---

Yes, Docker provides support for IPv6, but it is not enabled by default. To use IPv6, it must be explicitly enabled in the Docker daemon configuration.

Example configuration in daemon.json:

```json
{
  "ipv6": true,
  "fixed-cidr-v6": "2001:db8:1::/64"
}
```

Да, Docker поддерживает IPv6, но по умолчанию он отключён. Чтобы использовать IPv6, его нужно включить в конфигурации Docker daemon.

**43. How do you scale Docker containers horizontally?**

---

orizontal scaling in Docker means running multiple instances (replicas) of the same container/service and distributing traffic across them.

1. **Docker Compose** Scale a service to N replicas: `docker compose up -d --scale api=5`
   Then route traffic through a reverse proxy/load balancer (Traefik/Nginx) or rely on your setup (ports can’t be bound to the same host port by multiple replicas).

2. **Docker Swarm** Scale a service in a Swarm cluster: `docker service scale api=5` Swarm handles scheduling across nodes and provides built-in load balancing for services.

3. **Plain Docker** Run multiple containers manually: `docker run -d --name api-1 myapp` `docker run -d --name api-2 myapp`
   Then put a load balancer in front of them and keep the containers stateless.

Key requirements:

- Make the app stateless (store sessions/state in DB/Redis)

- Use health checks and load balancing

- Use an orchestrator (Swarm/Kubernetes) for production-scale reliability

Горизонтальное масштабирование Docker — это запуск нескольких экземпляров (реплик) одного сервиса и распределение трафика между ними.

1. **Docker Compose** Запуск N реплик: `docker compose up -d --scale api=5`
   Дальше нужен reverse proxy/балансировщик (Traefik/Nginx), потому что несколько реплик не могут одновременно занять один и тот же host-port.

2. **Docker Swarm** Масштабирование сервиса в кластере: `docker service scale api=5` Swarm сам распределит реплики по нодам и даст встроенную балансировку.

3. **Обычный Docker** Несколько контейнеров вручную: `docker run -d --name api-1 myapp` `docker run -d --name api-2 myapp`
   И дальше — балансировщик + stateless подход.

Ключевое:

- Делать сервис stateless

- Вынести состояние в DB/Redis

- Использовать health checks и балансировку

- Для production лучше оркестратор (Swarm/Kubernetes)

**44. What is the difference between the CMD and ENTRYPOINT instructions in a Dockerfile?**

--

CMD and ENTRYPOINT are Dockerfile instructions that define what command runs when a container starts, but they behave differently.

**CMD** - Provides the default command or arguments for the container. Can be overridden when running the container with docker run. Typically used to supply default parameters. Example: `CMD ["python", "app.py"]` Running: `docker run myimage` executes: `python app.py` But if you run: docker run myimage bash - the CMD is replaced by bash.

**ENTRYPOINT** - Defines the main executable of the container. It is not easily overridden by arguments passed with docker run. Additional parameters passed to docker run are appended as arguments.
Example: `ENTRYPOINT ["python"] CMD ["app.py"]` Running: `docker run myimage` executes: `python app.py` Running: `docker run myimage script.py` executes: `python script.py`

Key Difference

- CMD → default command or arguments (can be overridden).

- ENTRYPOINT → main command that always runs.

Often they are used together: ENTRYPOINT defines the executable, CMD provides default arguments.

CMD и ENTRYPOINT — это инструкции Dockerfile, которые определяют команду, выполняемую при запуске контейнера.
**CMD** Задаёт команду или аргументы по умолчанию. Может быть переопределена при запуске контейнера. Часто используется для передачи аргументов.
**ENTRYPOINT** Определяет основную команду контейнера. Обычно не заменяется аргументами docker run. Аргументы добавляются к ENTRYPOINT.

Основное отличие

- CMD — команда по умолчанию, легко переопределяется.

- ENTRYPOINT — основная команда контейнера.

Часто их используют вместе: ENTRYPOINT задаёт исполняемую программу, а CMD — аргументы по умолчанию.

**45. What is the purpose of volumes in Docker?**

---

Volumes in Docker are used to provide persistent storage for container data. Since containers are ephemeral, any data stored inside a container can be lost when the container is removed. Volumes allow data to exist outside the container lifecycle.

Main purposes of Docker volumes:

**Data Persistence** - Store data outside the container so it is not lost when the container stops or is deleted.

**Data Sharing** - Allow multiple containers to access and share the same data.

**Better Performance** - Volumes are managed by Docker and are more efficient than writing data directly to the container filesystem.

**Data Backup and Migration** - Volumes can be easily backed up, restored, or moved between hosts.

Example: `docker run -d -v myvolume:/app/data myimage`

This mounts the volume myvolume into the container directory /app/data.

Volumes в Docker используются для постоянного хранения данных контейнера. Контейнеры являются временными (ephemeral), поэтому данные внутри контейнера могут быть потеряны при его удалении. Volumes позволяют хранить данные вне контейнера.

Основные цели volumes:

**Постоянное хранение данных** - Данные сохраняются даже после остановки или удаления контейнера.

**Совместное использование данных** - Несколько контейнеров могут использовать один и тот же volume.

**Лучшая производительность** - Volumes работают быстрее, чем запись в файловую систему контейнера.

**Резервное копирование и перенос** - Данные volume можно легко бэкапить и переносить.

Пример: `docker run -d -v myvolume:/app/data myimage`

Volume myvolume монтируется в папку /app/data внутри контейнера.

**46. Is it possible for a container to restart by itself?**

---

Yes, a Docker container can restart automatically using restart policies. Restart policies tell Docker when a container should be restarted if it stops or crashes.

Common restart policies:

**no (default)** - The container does not restart automatically.

**on-failure** - The container restarts only if it exits with a non-zero status (error).

**always** - The container always restarts if it stops, even after Docker daemon restarts.

**unless-stopped** - The container restarts automatically unless it was manually stopped.

Example: `docker run -d --restart=always nginx`

This starts an nginx container that will automatically restart if it stops or if Docker restarts.

Да, контейнер Docker может автоматически перезапускаться. Для этого используются restart policies.

Основные политики перезапуска:

**no** — контейнер не перезапускается (по умолчанию).

**on-failure** — перезапуск только при ошибке.

**always** — контейнер всегда перезапускается.

**unless-stopped** — перезапускается, пока его не остановят вручную.

Пример: `docker run -d --restart=always nginx`

Контейнер nginx будет автоматически перезапускаться при остановке или перезапуске Docker.

**47. How do you expose ports in a Docker container?**
Ports in a Docker container are exposed using the -p option in docker run. Example: `docker run -p 8080:80 nginx` This maps port 8080 on the host to port 80 inside the container.

Порты в Docker открываются через параметр -p. Пример: `docker run -p 8080:80 nginx` Порт 8080 хоста → порт 80 контейнера.

**48. How do you pass environment variables to a Docker container?**

---

Environment variables are passed to a Docker container using the -e option. Example: `docker run -e APP_ENV=production nginx` You can also use an env file: `docker run --env-file .env nginx`

Переменные окружения передаются через параметр -e. Пример:`docker run -e APP_ENV=production nginx` Можно также использовать файл: `docker run --env-file .env nginx`

**49. What is the difference between Docker restart policies "no", "on-failure", and "always"?**

---

no — The container does not restart automatically (default).
on-failure — The container restarts only if it exits with an error (non-zero status).
always — The container always restarts if it stops, including after Docker daemon restart.

no — контейнер не перезапускается автоматически.
on-failure — перезапуск только при ошибке.
always — контейнер всегда перезапускается, даже после перезапуска Docker.

**50. What is the difference between a Docker image and a container?**

---

Docker Image — a read-only template that contains the application code, dependencies, and configuration needed to run a container.
Docker Container — a running instance of a Docker image where the application actually executes.
In short: Image = blueprint, Container = running instance.

Docker Image — это неизменяемый шаблон с кодом приложения, зависимостями и конфигурацией.
Docker Container — это запущенный экземпляр Docker-образа, в котором работает приложение.
Коротко: Image — шаблон, Container — запущенный экземпляр.

**51. How do you update a Docker image?**

To update a Docker image, you typically rebuild the image and recreate the container.

Steps:

- Update the Dockerfile or application code.

- Rebuild the image: `docker build -t myimage:latest .`

- Stop and remove the old container: `docker stop mycontainer` and `docker rm mycontainer`

- Run a new container with the updated image: ``docker run -d myimage:latest`

If the image is from a registry, you can also update it by pulling the latest version: `docker pull nginx`

Чтобы обновить Docker-образ:

- Изменить Dockerfile или код приложения.

- Пересобрать образ: `docker build -t myimage:latest .`

- Остановить и удалить старый контейнер: `docker stop mycontainer` и `docker rm mycontainer`

- Запустить новый контейнер с обновлённым образом.

Если образ из registry, можно просто скачать новую версию: `docker pull nginx`

**52. What is the purpose of the CMD instruction in a Dockerfile?**

---

CMD specifies the default command that runs when a container starts. It can be overridden when running the container with docker run. Example: `CMD ["python", "app.py"]`

CMD задаёт команду по умолчанию, которая выполняется при запуске контейнера. Её можно переопределить при запуске контейнера через docker run.

**53. How do you inspect the metadata of a Docker image?**

---

To inspect the metadata of a Docker image, use the command: `docker inspect image_name` Example: `docker inspect nginx`
This command shows detailed information such as configuration, layers, environment variables, network settings, and other metadata.

Чтобы посмотреть метаданные Docker-образа, используется команда: `docker inspect image_name` Пример: `docker inspect nginx`
Она показывает подробную информацию об образе: конфигурацию, слои, переменные окружения и другие метаданные.

**54. What is Docker Swarm?**

---

Docker Swarm is Docker’s native container orchestration tool used to manage a cluster of Docker nodes. It allows multiple Docker hosts to work together as a single system and manages containers as services.

Key features:

- Cluster management (manager and worker nodes)

- Service deployment and scaling

- Built-in load balancing

- Rolling updates and rollbacks

- Self-healing

Docker Swarm — это встроенный инструмент оркестрации Docker для управления кластером нод. Он объединяет несколько хостов в одну систему и управляет контейнерами как сервисами.

Основные функции:

- Управление кластером

- Деплой и масштабирование

- Балансировка нагрузки

- Rolling updates

- Автоматический перезапуск контейнеров

**55. How does Docker handle container isolation and security?**

---

Docker provides container isolation and security using Linux kernel features.

Main mechanisms:

- Namespaces — isolate system resources (processes, network, filesystem, users).

- cgroups — limit and control resource usage (CPU, memory, I/O).

- Union filesystem — provides isolated layered filesystems for containers.

- Capabilities — restrict Linux privileges for containers.

- Seccomp profiles — limit system calls available to containers.

These mechanisms ensure containers run in isolated environments and cannot easily interfere with the host or other containers.

Docker обеспечивает изоляцию и безопасность контейнеров с помощью механизмов ядра Linux.

Основные механизмы:

- Namespaces — изоляция процессов, сети и файловой системы.

- cgroups — ограничение использования ресурсов (CPU, память).

- Union filesystem — изолированная слоистая файловая система.

- Capabilities — ограничение привилегий.

- Seccomp — ограничение системных вызовов.

Эти механизмы обеспечивают безопасную и изолированную работу контейнеров.

**56. What are the benefits of using Docker in a microservices architecture?**

---

Docker is well suited for microservices because it allows each service to run in its own isolated container.

Main benefits:

- Service Isolation — each microservice runs in its own container with its own dependencies.

- Scalability — services can be scaled independently.

- Portability — containers run the same in development, testing, and production.

- Faster Deployment — lightweight containers start quickly.

- Simplified Dependency Management — each service includes its own libraries and runtime.

- Better Resource Utilization — containers share the host OS kernel and use fewer resources than VMs.

Docker хорошо подходит для микросервисной архитектуры, потому что каждый сервис может работать в отдельном контейнере.

Основные преимущества:

- Изоляция сервисов — каждый микросервис работает отдельно.

- Масштабируемость — сервисы можно масштабировать независимо.

- Переносимость — одинаковая среда в dev, test и production.

- Быстрый деплой — контейнеры запускаются быстро.

- Управление зависимостями — каждый сервис имеет свои зависимости.

- Эффективное использование ресурсов — меньше ресурсов, чем у виртуальных машин.

**57. How do you debug issues in a Docker container?**

---

To debug issues in a Docker container, I usually do:

- Check logs: docker logs <container>

- Inspect container details: docker inspect <container>

- Enter the container: docker exec -it <container> sh (or bash)

- Check running processes: docker top <container>

- Monitor resource usage: docker stats <container>

- View events: docker events

Для отладки контейнера обычно делаю так:

- Смотрю логи: docker logs <container>

- Проверяю детали: docker inspect <container>

- Захожу внутрь: docker exec -it <container> sh (или bash)

- Смотрю процессы: docker top <container>

- Мониторю ресурсы: docker stats <container>

- Смотрю события: docker events

**58. What is the purpose of the "docker exec" command?**

---

The docker exec command is used to run a command inside a running container. Example: `docker exec -it mycontainer bash` This opens an interactive shell inside the container.

Команда docker exec используется для выполнения команды внутри работающего контейнера. Пример: `docker exec -it mycontainer bash` Открывает интерактивный терминал внутри контейнера.

**59. How do you limit the CPU and memory usage of a Docker container?**

---

You can limit CPU and memory when starting a container using docker run options.

Example: `docker run -d --cpus="1.5" --memory="512m" nginx`

--cpus → limits CPU usage

--memory → limits RAM usage

Ограничить CPU и память можно при запуске контейнера.

Пример: `docker run -d --cpus="1.5" --memory="512m" nginx`

--cpus — ограничение CPU

--memory — ограничение RAM

**60. What is the significance of the "Dockerfile.lock" file?**

---

Docker itself does not have a standard file called Dockerfile.lock. Usually, when people mention Dockerfile.lock, they mean a lock file used to fix exact dependency versions during image builds (similar to requirements.txt, package-lock.json, or poetry.lock).

The purpose of such lock files is:

- Ensure reproducible builds

- Prevent unexpected dependency changes

- Guarantee the same versions are installed each time the image is built

В Docker нет стандартного файла Dockerfile.lock. Обычно под этим подразумевают lock-файл зависимостей, который фиксирует точные версии пакетов.

Цель таких файлов:

- Обеспечить воспроизводимую сборку образа

- Избежать случайных обновлений зависимостей

- Гарантировать одинаковые версии при каждом build.

**61.How do you create a multi-stage build in Docker?**

---

A multi-stage build in Docker uses multiple FROM instructions in a Dockerfile to separate build and runtime environments.

Example:

```yml
FROM python:3.11 AS builder
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt

FROM python:3.11-slim
WORKDIR /app
COPY --from=builder /app /app
CMD ["python", "app.py"]
```

This allows you to build the application in one stage and copy only the necessary files into the final image, making the image smaller and more secure.

Multi-stage build создаётся с помощью нескольких инструкций FROM в Dockerfile. Первый stage используется для сборки, второй — для финального контейнера.
Это позволяет копировать только нужные файлы в итоговый образ, уменьшая его размер и повышая безопасность.
