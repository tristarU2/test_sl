Коллега Дмитрий недавно узнал, что в свежей Ubuntu появилась новая фишка, и хочет её поскорее протестировать на нашем многострадальном docker-хосте.
Он попросил вас:

- запустить контейнер task7 c Ubuntu версии 20.04,
- примонтировать в контейнер каталог /etc/systemd/system/default.target.wants/ с хоста в любой новый каталог,
- зайти в контейнер с ubuntu и скопировать из контейнера на хост файл /etc/systemd/system/default.target.wants/e2scrub_reap.service.

После этого вам также нужно оставить контейнер запущенным и сделать так, чтобы он пережил рестарт.


docker run \
  --name=task7 \
  --network=bridge \
  --restart=always \
  -d \
  -e SUDO_USER \
  -v /etc/systemd/system/default.target.wants:/srv/systemd \
  ubuntu:20.04 bash \
  -c 'while true; do echo "Hello, $SUDO_USER"; sleep 15; done'