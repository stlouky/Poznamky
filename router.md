# Nastavení statické IP adresy na routeru Synology

Tento návod poskytuje krok za krokem instrukce, jak nastavit statickou IP adresu pro zařízení na routeru Synology.

## Požadavky

- Router Synology
- Administrativní přístup k routeru Synology
- MAC adresa zařízení

## Kroky pro nastavení statické IP adresy

### Krok 1: Přístup k administračnímu rozhraní routeru Synology

1. Otevřete webový prohlížeč a zadejte IP adresu vašeho routeru Synology.
   - Příklad: `http://192.168.1.1`
2. Přihlaste se pomocí svého administrátorského uživatelského jména a hesla.

### Krok 2: Navigace do Network Center

1. Po přihlášení klikněte v hlavním menu na `Network Center`.
2. V bočním panelu vyberte `Local Network`.

### Krok 3: Přiřazení statické IP adresy

1. V sekci `Local Network` přejděte na záložku `DHCP`.
2. Klikněte na záložku `Static IP`.
3. Klikněte na tlačítko `Create` pro přidání nového přiřazení statické IP adresy.

### Krok 4: Zadání informací o zařízení

1. **MAC Adresa**: Zadejte MAC adresu zařízení, kterému chcete přiřadit statickou IP adresu. Tuto adresu obvykle naleznete v nastavení sítě zařízení nebo na štítku na zařízení.
   - Příklad: `2C:F0:5D:A9:F3:F8`
2. **Hostname**: Zadejte název zařízení (volitelně).
   - Příklad: `mazlik`
3. **IP Adresa**: Zadejte statickou IP adresu, kterou chcete zařízení přiřadit, např. `192.168.1.200`.
   - Příklad: `192.168.1.200`

### Krok 5: Uložení a použití nastavení

1. Klikněte na `OK` pro uložení nového přiřazení statické IP adresy.
2. Ujistěte se, že nová statická IP adresa je zobrazena v seznamu přiřazení statických IP adres.
3. Restartujte zařízení, aby získalo novou statickou IP adresu.

### Krok 6: Ověření konfigurace

1. Po restartování zařízení ověřte, že získalo statickou IP adresu.
2. To můžete zkontrolovat v `Network Center` pod `Device List` nebo v nastavení sítě zařízení.

## Řešení problémů

- Pokud zařízení nezíská statickou IP adresu, ujistěte se, že zadaná MAC adresa je správná.
- Zkontrolujte, že statická IP adresa není v rozsahu DHCP poolu nebo není již přiřazena jinému zařízení.
- Restartujte jak router Synology, tak i zařízení, aby se obnovila nastavení sítě.

## Další zdroje

- Dokumentace routeru Synology: [Oficiální dokumentace Synology](https://www.synology.com/en-global/knowledgebase)
- Podpora na fóru: [Komunita Synology](https://community.synology.com)
