### Maintener Ahdian Rawuli ###

## Cara install

1. apt install docker
2. apt install docker-compose

## Cara running

docker-compose -f compose.yml up --build -d

## Cek status service

http://IP-HOST:7070/status

## format HLS

Contoh nama video adalah :
- test360.mp4
- test480.mp4
- test720.mp4

maka format HLS adalah :

http://IP-HOST:7070/hls/test,360p.mp4,480p.mp4,720p.mp4,.urlset/master.m3u8

## Struktur services

f = File

d = Directory

[f] compose.yml -> config untuk docker

[f] entrypoint.sh -> untuk menjalankan nginx

[d] config -> untuk mount file nginx.conf ke container

[d] images -> untuk build images alpine ke service stremming

[d] log -> berisi log webserver

[d] videos -> disini untuk upload video

## Test VOD Streammer

Buka http://demo.jwplayer.com/developer-tools/http-stream-tester

Paste http://IP-HOST:7070/hls/test,360p.mp4,480p.mp4,720p.mp4,.urlset/master.m3u8 ke field "FILE URL" dan klik TEST STREAM

