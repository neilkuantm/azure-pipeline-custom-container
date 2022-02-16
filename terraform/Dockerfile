FROM hashicorp/terraform

RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
  && apk add bash sudo shadow nodejs \
  && apk del .pipeline-deps
  
RUN apk add gcc musl-dev python3-dev libffi-dev openssl-dev cargo make && \
pip install --upgrade pip && \
pip install azure-cli

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

ENTRYPOINT [""]

CMD ["node"]
