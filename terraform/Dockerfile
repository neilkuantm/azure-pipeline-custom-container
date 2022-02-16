FROM hashicorp/terraform
RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
  && apk add bash sudo shadow nodejs && \
  && apk del .pipeline-deps && echo '#!/bash/bash' >> /entrypoint.sh && echo 'tail -f /etc/hosts' >> /entrypoint.sh && chmod +x /entrypoint.sh

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

ENTRYPOINT ["entrypoint.sh"]
