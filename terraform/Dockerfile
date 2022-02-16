FROM hashicorp/terraform
COPY entryponit.sh /
RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
  && apk add bash sudo shadow nodejs && chmod +x entryponit.sh \
  && apk del .pipeline-deps

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

ENTRYPOINT ["entryponit.sh"]
