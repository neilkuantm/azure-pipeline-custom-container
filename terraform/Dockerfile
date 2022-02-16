FROM hashicorp/terraform

RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
  && apk add bash sudo shadow nodejs \
  && apk del .pipeline-deps

RUN apk add gcc musl-dev python3-dev libffi-dev openssl-dev cargo make py3-pip

RUN groupadd --gid 1001 user                                                                                      \
  && useradd --shell /bin/bash --comment "Sudo User" --uid 1001 --gid 1001 --no-log-init --groups user     \
  && echo "%user ALL = (ALL) NOPASSWD: ALL" >> /etc/sudoers.d/nopasswd                                                  \
  && chmod 0440 /etc/sudoers.d/nopasswd

USER user:user
RUN pip3 install azure-cli

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

ENTRYPOINT [""]

CMD ["node"]
