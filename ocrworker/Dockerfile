FROM ubuntu

RUN apt-get update
RUN apt-get -q -y install git golang tesseract-ocr

ENV GOPATH /opt/go
RUN mkdir -p $GOPATH

RUN go get -u -v github.com/maiduchuy/open-ocrworker

# build open-ocr-preprocessor binary and copy it to /usr/bin
RUN cd $GOPATH/src/github.com/maiduchuy/open-ocrworker/cli-worker && go build -v -o open-ocr-worker && cp open-ocr-worker /usr/bin