
### **Q1: What is a key difference between containers and virtual machines (VMs)?**

**✅ Answer: C. Containers share the host OS kernel**

**Explanation:**
Containers don’t need their own full operating system—they just share the host’s kernel. This makes them much faster and lighter than VMs, which run a full OS for each instance.

---

### **Q2: What is the role of Docker's container runtime?**

**✅ Answer: D. Creates and runs containers from images**

**Explanation:**
The container runtime is the engine under the hood. It takes images and turns them into running containers, handling how they start, stop, and interact with the system.

---

### **Q3: Which Docker CLI command lists running containers?**

**✅ Answer: A. `docker ps`**

**Explanation:**
Think of `docker ps` like “process status” for containers—it shows what’s currently running. Add `-a` if you want to see everything, even stopped containers.

---

### **Q4: What does the Docker daemon (`dockerd`) do?**

**✅ Answer: B. Interacts with the Linux kernel to manage containers**

**Explanation:**
The Docker daemon is the boss in the background. It listens for Docker commands and talks to the kernel to manage containers, images, volumes, and more.

---

### **Q5: Which Linux namespace isolates process IDs?**

**✅ Answer: C. `pid`**

**Explanation:**
The PID namespace keeps process IDs separate. So, each container can have its own process tree without interfering with others or the host.

---

### **Q6: What is the purpose of cgroups in Linux?**

**✅ Answer: C. Restrict resource usage**

**Explanation:**
Cgroups are like traffic cops for resources. They make sure containers don’t hog all the CPU, memory, or disk I/O, keeping the system stable.

---

### **Q7: In a Dockerfile, what does each `RUN` instruction do?**

**✅ Answer: B. Adds a new layer to the image**

**Explanation:**
Every `RUN` command builds a new layer in your Docker image. These layers help with caching and rebuilding faster when nothing changes.

---

### **Q8: What is the default Docker network driver used by Compose?**

**✅ Answer: C. `bridge`**

**Explanation:**
By default, Docker Compose connects your services using a `bridge` network. It’s like giving them their own private LAN so they can talk to each other.

---

### **Q9: Which command removes all dangling images (not in use)?**

**✅ Answer: C. `docker image prune`**

**Explanation:**
This command cleans up unused image layers that are just taking up space—kind of like taking out the Docker trash.

---

### **Q10: What is the correct order of the container lifecycle?**

**✅ Answer: B. create → start → stop → rm**

**Explanation:**
This is the typical flow:

1. **Create** the container from an image.
2. **Start** it to run.
3. **Stop** it when done.
4. **Remove** it to free resources.

