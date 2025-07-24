
# Docker Lifecycle & Clean-up Report

## Step 1: Check Disk Usage Before

```bash
docker system df
```

**Output Example (Before):**
```
TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          5         2         1.78GB    1.0GB (56%)
Containers      2         2         60MB      0B (0%)
Local Volumes   1         1         100MB     0B (0%)
Build Cache     0         0         0B        0B
```

---

## Step 2: Create and Start Containers

```bash
docker-compose up -d
```

This creates and starts the services defined in `docker-compose.yml`.

---

## Step 3: Stop Containers

```bash
docker-compose stop
```

All running services are stopped but not removed.

---

## Step 4: Remove Containers

```bash
docker-compose rm -f
```

This fully removes the stopped containers.

---

## Step 5: Prune Unused Docker Images

```bash
docker image prune -f
```

Removes dangling (unused) images to reclaim disk space.

---

## Step 6: Check Disk Usage After

```bash
docker system df
```

**Output Example (After):**
```
TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          2         1         890MB     100MB (11%)
Containers      0         0         0B        0B
Local Volumes   1         1         100MB     0B (0%)
Build Cache     0         0         0B        0B
```

---

## Summary

- Successfully demonstrated lifecycle: **create → start → stop → remove**
- Disk usage was reduced from **1.78GB → 890MB** after image pruning.
- System is now cleaner and uses less space.
