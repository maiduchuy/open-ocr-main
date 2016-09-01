FROM ubuntu

RUN apt-get update
RUN apt-get -q -y install git golang tesseract-ocr

ENV GOPATH /opt/go
RUN mkdir -p $GOPATH

RUN go get -u -v github.com/maiduchuy/convert-pdf

# build open-ocr-preprocessor binary and copy it to /usr/bin
RUN cd $GOPATH/src/github.com/maiduchuy/convert-pdf/cli-preprocessor && go build -v -o open-ocr-preprocessor && cp open-ocr-preprocessor /usr/bin