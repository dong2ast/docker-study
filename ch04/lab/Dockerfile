FROM diamol/golang AS builder

WORKDIR web
COPY main.go .
RUN go build -o /web/server
RUN chmod +x /web/server

FROM diamol/base

CMD ["/web/server"]
ENV USER=sixeyed
EXPOSE 80

COPY --from=builder /web/server .
COPY index.html .

