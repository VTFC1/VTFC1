{
  "routing": {
    "domainStrategy": "IPIfNonMatch" // Define a estratégia de roteamento de domínio
  },
  "inbounds": [
    {
      "listen": "127.0.0.1", // Endereço IP para ouvir conexões
      "port": 10808, // Porta para ouvir conexões
      "protocol": "socks", // Protocolo de entrada (SOCKS)
      "settings": {
        "auth": "password", // Método de autenticação (senha)
        "accounts": [ // Lista de contas de usuário permitidas
          {
            "user": "my_user", // Nome de usuário
            "pass": "my_password", // Senha
            "level": 8 // Nível de acesso do usuário
          }
        ]
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "vmess", // Protocolo de saída (VMess)
      "settings": {
        "vnext": [
          {
            "address": "sg4-v2ray.sshkit.org", // Endereço do servidor de destino
            "port": 443, // Porta do servidor de destino
            "users": [
              {
                "id": "c6747da4-fb2e-4a2a-bdb7-8614bdd6b0b3", // ID do usuário
                "alterId": 64, // Valor de alteração de ID
                "security": "auto" // Nível de segurança (automático)
              }
            ]
          }
        ]
      }
    }
  ],
  "log": {
    "loglevel": "warning" // Nível de registro (aviso)
  },
  "dns": {
    "servers": [ // Servidores DNS para resolver consultas de DNS
      "1.1.1.1", // Cloudflare DNS
      "8.8.8.8" // Google DNS
    ]
  }
}