FROM hashicorp/terraform
RUN echo '#!/bin/bash' >> /entrypoint.sh && echo 'tail -f /etc/hosts' >> /entrypoint.sh && chmod +x /entrypoint.sh
RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
  && apk add bash sudo shadow nodejs \
  && apk del .pipeline-deps

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

ENTRYPOINT ["/entrypoint.sh"]
