# Projektový název

Krátký popis projektu.

## Obsah

1. [Úvod](#úvod)
2. [Požadavky](#požadavky)
3. [Instalace](#instalace)
4. [Konfigurace sítě](#konfigurace-sítě)
5. [Spuštění serveru](#spuštění-serveru)
6. [Použití](#použití)
7. [Přispívání](#přispívání)
8. [Licence](#licence)

## Úvod

Detaily o projektu, co dělá a proč byl vytvořen.

## Požadavky

Seznam softwaru a nástrojů potřebných pro běh projektu:

- Ubuntu 20.04 nebo novější
- Netplan
- NetworkManager
- Git
- Další požadavky

## Instalace

Postupujte podle následujících kroků pro instalaci projektu.

1. Klonování repozitáře:
    ```bash
    git clone https://github.com/uzivatelske-jmeno/projekt.git
    cd projekt
    ```

2. Instalace závislostí:
    ```bash
    sudo apt-get update
    sudo apt-get install <seznam-zavislosti>
    ```

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
