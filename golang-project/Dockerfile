# first stage

FROM golang:1.18.2-buster as build

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 go build -o build/fizzbuzz

# second stage

FROM gcr.io/distroless/static

COPY --from=build /app/build/fizzbuzz /app/fizzbuzz

EXPOSE 8080

CMD ["/app/fizzbuzz"]