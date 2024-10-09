FROM registry.access.redhat.com/ubi9/python-312:latest

ENV GOVC_VERSION="v0.30.7"

COPY requirements.txt ${APP_ROOT}
# Install the dependencies
RUN pip install -r ${APP_ROOT}/requirements.txt

RUN wget -O /tmp/govc.tar.gz https://github.com/vmware/govmomi/releases/download/${GOVC_VERSION}/govc_Linux_x86_64.tar.gz && \
    tar -xvf /tmp/govc.tar.gz -C /tmp && \
    mv /tmp/govc ${APP_ROOT}/bin && \
    rm /tmp/govc* && \
    wget -O ${APP_ROOT}/bin "https://mirror2.openshift.com/pub/openshift-v4/clients/butane/latest/butane" && \
    chmod +x ${APP_ROOT}/bin/butane
