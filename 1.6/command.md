https://www.binarycarpenter.com/2-easy-steps-to-configure-docker-logging-with-rsyslog/

docker run \
  --name=task5 \
  --network=bridge \
  --restart=always \
  -d \
  -e SUDO_USER \
  ubuntu:22.04 bash \
  -c 'while true; do echo "Hello, $SUDO_USER"; sleep 2; done'



docker run -it --name=task5 -e SUDO_USER ubuntu:22.04 bash -c "while true; do echo 'Hello, $SUDO_USER"; sleep 2; done'