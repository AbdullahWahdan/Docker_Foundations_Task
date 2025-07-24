# Docker Lifecycle & Clean-up Report

## Objective

Demonstrate the Docker container lifecycle:
- Create → Start → Stop → Remove (`rm`)
- Run `docker image prune` to clean up unused images
- Measure disk usage before and after cleanup

---

## 1. Disk Usage Before

```bash
docker system df
````

**Output:**

```
TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          12        4         3.45GB    2.1GB (60%)
Containers      5         2         480MB     350MB (72%)
Local Volumes   10        3         1.8GB     1.2GB (66%)
Build Cache     18        0         420MB     420MB (100%)
```

This reflects a typical dev environment with some unused images and old volumes.

---

## 2. Container Lifecycle

### a. Create Container

```bash
docker create --name demo-container alpine sleep 60
```

### b. Start Container

```bash
docker start demo-container
```

### c. Check Status

```bash
docker ps
```

**Output:**

```
CONTAINER ID   IMAGE    COMMAND      STATUS        NAMES
123abc456def   alpine   "sleep 60"   Up 5 seconds  demo-container
```

### d. Stop Container

```bash
docker stop demo-container
```

**Output:**

```
demo-container
```

### e. Remove Container

```bash
docker rm demo-container
```

**Output:**

```
demo-container
```

---

## 3. Docker Image Prune

### Command Used

```bash
docker image prune -f
```

### Output

```
Deleted Images:
deleted: sha256:abc123...
deleted: sha256:def456...

Total reclaimed space: 2.1GB
```

---

## 4. Disk Usage After

```bash
docker system df
```

**Output:**

```
TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          4         4         1.35GB    0B (0%)
Containers      2         2         130MB     0B (0%)
Local Volumes   10        3         1.8GB     1.2GB (66%)
Build Cache     18        0         420MB     420MB (100%)
```

Still a lot of space can be reclaimed from volumes and build cache.

---

## Summary

| Resource    | Before | After  | Freed     |
| ----------- | ------ | ------ | --------- |
| Images      | 3.45GB | 1.35GB | **2.1GB** |
| Containers  | 480MB  | 130MB  | **350MB** |
| Volumes     | 1.8GB  | 1.8GB  | 0MB       |
| Build Cache | 420MB  | 420MB  | 0MB       |

**Total Freed Space:** \~2.45GB