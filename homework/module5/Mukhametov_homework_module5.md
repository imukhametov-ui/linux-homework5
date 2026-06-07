# Homework Module 5

## Завдання 1 Мережева діагностика

bash
ip a
ping 8.8.8.8
ss -tulpn

Коментар:
Команда ip a показала мережеві інтерфейси та локальну IP-адресу.
Після ping 8.8.8.8 видно, що доступ до інтернету є.
Команда ss -tulpn показала listening-порти, наприклад ssh слухає порт 22.

## Завдання 2. SSH-доступ з ключами та config

bash
sudo apt update
sudo apt install openssh-server
systemctl status ssh
ssh ubuntu@localhost
ssh-keygen
ssh-copy-id ubuntu@localhost
ssh ubuntu@localhost
nano ~/.ssh/config
ssh myserver


Коментар:

Було встановлено openssh-server та перевірено роботу ssh.service.
Host у config: myserver. Після копіювання ключа підключення ssh myserver працює без введення пароля.
## Завдання 3 Копіювання файлів між машинами

bash
echo "test" > test.txt
scp test.txt myserver:/home/ubuntu/
ssh myserver "mkdir -p /home/ubuntu/sync_dir"
mkdir -p local_sync
cp test.txt local_sync/
rsync -av local_sync/ myserver:/home/ubuntu/sync_dir/
sftp myserver
ls
cd sync_dir
ls
bye


Коментар:
окальний файл test.txt був переданий на сервер через scp. Для синхронізації створено директорію /home/ubuntu/sync_dir та використано rsync. Наявність файлу перевірено через sftp командою ls.

Шлях до файлів на сервері:
/home/ubuntu/sync_dir/

Команда перевірки:
ls (всередині sftp)
