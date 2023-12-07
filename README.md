<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2023/08/logo-github-cwmkt.svg" alt="DispZap Whats Marketing" width="240" />
<p align="center">WireGuard é um aplicativo de software e protocolo de comunicação gratuito e de código aberto. Ele é usado para implementar técnicas de rede virtual privada na criação de conexões seguras de ponto a ponto em configurações roteadas ou de ponte.
🚀</p>
</p>
  
<p align="center">
<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
<span>Grupo WhatsaAPP: </span>
<a href="https://chat.whatsapp.com/LOUXV1cWn0O1hQaz37xiRa" target="_blank">Grupo</a>
</p>

<hr />
<hr />

![image](https://github.com/cwmkt/wireguard/assets/34479816/5b6e1b8f-154a-47dd-a09a-ca191cd93a14)

### Instalação com Docker

Se você ainda não instalou o Docker, instale-o executando:

```bash
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker $(whoami)
```
```bash
exit
```
Faça login novamente!

### Inicie o WireGuard
Para instalar e executar automaticamente o wg-easy, basta executar:

```bash
docker run -d \
  --name=wg-easy \
  -e WG_HOST=🚨 SEU_SERVER_IP \
  -e PASSWORD=🚨 SUA_ADMIN_PASSWORD \
  -v ~/.wg-easy:/etc/wireguard \
  -p 51820:51820/udp \
  -p 51821:51821/tcp \
  --cap-add=NET_ADMIN \
  --cap-add=SYS_MODULE \
  --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
  --sysctl="net.ipv4.ip_forward=1" \
  --restart unless-stopped \
  weejewel/wg-easy
```

💡 Substitua `SEU_SERVER_IP` pelo seu IP WAN ou um nome de host DNS dinâmico.
💡 Substitua `SUA_ADMIN_PASSWORD` por uma senha para fazer login na interface da web.

pronto! Agora só acessar o painel pelo endereço `http://0.0.0.0:51821`
