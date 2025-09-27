Role Name
=========

Ansible-роль для деплоя веб-приложения с помощью Docker Compose

Requirements
------------

Docker, Docker Compose

Role Variables
--------------
env - переменные окружения для сервиса (пока фиксированные).
```yaml
env:
  site_url: "https://freshwave-kmv.ru"

  tg_bot_token: ""
  tg_chat_id: ""

  phone_number: "+79966309098"
  tg_channel: "https://t.me/FreshWave26"
  vk_public: "https://vk.com/freshwavekmv"
  ig_profile: "https://instagram.com/dekabrist.ch"

  folder_id: ""
  google_creds: "{}"
```

image - информация об образе и теге сервиса.
```yaml
image:
  name: "puck3/freshwave"
  tag: "latest"
```

hostname - доменное имя.
```yaml
hostname: "freshwave-kmv.online"
```

email - адрес электронной почты.
```yaml
email: "shipilovk04@gmail.com"
```

docker_comopse_dir - директория, в которой будут находиться файлы docker-compose.yml и .env.
```yaml
docker_compose_dir: "/opt/freshwave"
```

Example Playbook
----------------
```yaml
---
- hosts: servers
  become: true
  roles:
      - role: freshwave_kmv.docker_compose_deploy
        hostname: "example.com"
        email: "mail@example.com"
```

License
-------

MIT
