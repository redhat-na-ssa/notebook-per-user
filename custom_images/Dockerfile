FROM image-registry.openshift-image-registry.svc:5000/redhat-ods-applications/s2i-minimal-notebook:2024.2

COPY requirements.txt /opt/app-root/bin/

RUN pip install -r /opt/app-root/bin/requirements.txt && rm /opt/app-root/bin/requirements.txt