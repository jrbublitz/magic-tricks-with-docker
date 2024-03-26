# First stage building 
FROM golang:alpine3.19 AS builder

WORKDIR /var/app

COPY . .

RUN go build -o /var/app/runner

# Second stage building

FROM scratch

COPY --from=builder /var/app/runner /runner

ENTRYPOINT ["/runner"]