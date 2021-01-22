FROM golang:1.15 as base

LABEL maintainer="Aliaksandr Sazankou <sazankou.a@gmail.com> itmakers.cz"

RUN mkdir /gapi

ADD . /gapi

WORKDIR /gapi

RUN go build -o gapi .

CMD ["/gapi/gapi"]
#
#RUN go get -u github.com/itmakerscz/gapi

#WORKDIR /gapi

#ENV GO111MODULE=on 
#ENV GOFLAGS=-mod=vendor
#ENV APP_USER app
#ENV APP_HOME /go/src/gapi

#ARG GROUP_ID
#ARG USER_ID

#RUN groupadd --gid $GROUP_ID app && useradd -m -l -uid $USER_ID --gid $GROUP_ID $APP_USER
#RUN mkdir -p $APP_HOME && chown -R $APP_USER:$APP_USER $APP_HOME

#USER $APP_USER
#WORKDIR $APP_HOME
#EXPOSE 8010
#CMD ["gapi"]
#ENV CGO_ENABLED=0 GOOS=linux GOARCH=amd64

#COPY go.mod .
#COPY go.sum .

#RUN go mod download

#COPY . .

#RUN go build -o gapi .

#EXPOSE 9090

#CMD ["GApi"]
#FROM alpine:latest as certs
#RUN apk --update add ca-certificates

#FROM scratch as app
#COPY --from=certs /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/ca-certificates.crt
#COPY --from=base /gapi /gapi
#ENTRYPOINT ["/gapi"]
#CMD ["./gapi"]
