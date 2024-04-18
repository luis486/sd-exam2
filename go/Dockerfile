# Utilizamos una imagen de Go específica
FROM golang:1.14.2

# Establecemos el directorio de trabajo dentro del contenedor
WORKDIR /go/app

# Agregamos todos los archivos del directorio actual al directorio de trabajo del contenedor
ADD . .

# Compilamos la aplicación antes de ejecutarla
RUN go build -o main .

EXPOSE 8080

# Comando para ejecutar la aplicación al iniciar el contenedor
CMD ["./main"]
