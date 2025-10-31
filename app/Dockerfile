FROM golang:1.25.3-alpine3.22 AS build

WORKDIR /app

COPY . .

RUN go build -o main cmd/api/main.go

FROM scratch

ENV PORT=8080

COPY --from=build /app/main .

CMD ["/main"]