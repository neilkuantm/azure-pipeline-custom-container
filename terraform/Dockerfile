FROM hashicorp/terraform
COPY . /
RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
  && apk add bash sudo shadow nodejs && chmod +x entrypoint.sh \
  && apk del .pipeline-deps

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

ENTRYPOINT ["entrypoint.sh"]
