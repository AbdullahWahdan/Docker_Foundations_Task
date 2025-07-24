# Stage 1
FROM alpine:latest AS builder
RUN echo "Hello Containers" > /message.txt

# Stage 2
FROM alpine:latest
COPY --from=builder /message.txt /message.txt
CMD ["cat", "/message.txt"]
#you can find the image pushed to my registry @ https://hub.docker.com/r/aw033/hello-containers
