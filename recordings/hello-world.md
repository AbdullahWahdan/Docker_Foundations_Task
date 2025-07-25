
# Hello World Container Demo

## 🎯 Objective

Run a simple Docker container to test the Docker engine setup, map a random port from the container to the host, name the container explicitly, and explain each CLI flag used.

---

## 🚀 Command Used

```bash
docker run --name hello-test -P hello-world
````

---

## 🧩 CLI Flags Breakdown

| Flag                | Explanation                                                                        |
| ------------------- | ---------------------------------------------------------------------------------- |
| `run`               | Tells Docker to create and start a new container                                   |
| `--name hello-test` | Assigns the container a custom name (`hello-test`) instead of a random one         |
| `-P`                | Publishes **all exposed ports** from the container to **random ports** on the host |
| `hello-world`       | The official Docker image to run. It prints a confirmation message and exits       |

> 🔸 Note: `hello-world` does **not expose ports**, so `-P` has no effect here. It’s included only to meet the project requirement.
## 📁 Deliverable

A terminal recording was created and saved to:

```
recordings/hello-world.cast
```

Use `asciinema play recordings/hello-world.cast` to replay the session.

---