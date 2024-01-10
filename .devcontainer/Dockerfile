FROM debian:12.4
RUN apt-get update && apt-get install -y openssh-client ansible ansible-lint
RUN apt-get install -y usbmuxd libimobiledevice6 libimobiledevice-utils
RUN useradd -m user
RUN mkdir -p /home/user/.ssh && ln -s /run/secrets/user_ssh_key /home/user/.ssh/id_rsa
RUN chown -R user:user /home/user/.ssh
RUN echo "Host *.trabe.io\n\tStrictHostKeyChecking no\n" >> /home/user/.ssh/config
USER user
ENV LC_ALL="C.UTF-8"
