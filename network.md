
## Konfigurace sítě

### Nastavení statické IP adresy pomocí Netplan

1. Otevřete nebo vytvořte konfigurační soubor pro Netplan:
    ```bash
    sudo nano /etc/netplan/01-network-manager-all.yaml
    ```

2. Upravte soubor následovně:
    ```yaml
    network:
      version: 2
      renderer: NetworkManager
      ethernets:
        enp37s0:
          dhcp4: no
          addresses:
            - 192.168.1.200/24
          routes:
            - to: 0.0.0.0/0
              via: 192.168.1.1
          nameservers:
            addresses:
              - 8.8.8.8
              - 8.8.4.4
    ```

3. Aplikujte změny:
    ```bash
    sudo netplan apply
    ```

4. Zkontrolujte nastavení sítě:
    ```bash
    ip a show enp37s0
    ip route
    ```

### Konfigurace připojení v NetworkManageru

1. Zkontrolujte připojení:
    ```bash
    nmcli connection show
    ```

2. Odstraňte stará připojení, pokud existují:
    ```bash
    nmcli connection delete <UUID-starého-připojení>
    ```

3. Restartujte NetworkManager:
    ```bash
    sudo systemctl restart NetworkManager
    ```

## Spuštění serveru

Popis, jak spustit serverovou aplikaci.

```bash
# Příklad spuštění serveru
./start-server.sh
