FROM golang as buider 
WORKDIR /src
COPY src .
RUN CGO_ENABLED=0 go build -o app
FROM scratch
ADD ./html /html
COPY --from=buider /src/app .
ENTRYPOINT [ "/app" ]
EXPOSE 8080