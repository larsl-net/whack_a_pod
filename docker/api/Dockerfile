FROM golang as builder

ADD apps/api/ /app

WORKDIR /app

RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o "/main" "/app/main.go"


FROM scratch

COPY --from=builder main /

CMD ["/main"]

