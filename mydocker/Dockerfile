FROM garland/butterfly:latest

RUN apt-get update \
 && apt-get install -y -q --no-install-recommends \
    curl \
    git \
 && apt-get clean \
 && rm -r /var/lib/apt/lists/*

ADD wrk.gz /opt/app
ADD test.lua /opt/app

EXPOSE 57575

ENTRYPOINT ["/usr/bin/python", "/usr/local/bin/butterfly.server.py", "--unsecure", "--host=0.0.0.0", "--port=57575"]
