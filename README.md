# Homelab
Moje zrealizowane projekty w ramach homelabu

1. Urządzenia sieciowe:

a. Rutery
- Wyłączenie niepotrzebnych funkcji na urządzeniach sieciowych jak telnet, ftp itd. w celu zwiększenia bezpieczeństwa w sieci domowej.
- Konfiguracja rutera od operatora, wyłączenie rozgłaszania WiFi, ustawienie limitów danych, analiza logów.
- Instalacja alternatywnego oprogramowania Gargoyle na ruterze TP-Linka, ustawienie QoS i limitów pobierania dla poszczególnych urządzeń w celu ograniczenia wysycenia łącza internetowego.

b. Przełączniki
- Konfiguracja przełączników TP-Link, mikrotik
- Agregacja interfejsów na mikrotiku, poprawienie kultury pracy interfejsów SFP+.

c. Punkty dostępowe
- Konfiguracja rutera Mikrotik RB951 jako osobny AP i wzmacniacz sygnału WiFi z tym samym SSID co sieć główna.
- Konfiguracja AP Ubiquity UAP-AC-LR LR Long Range za pośrednictwem aplikacji na telefon i kontrolera Unifi zainstalowanym na maszynie wirtualnej w Proxmox.  Utworzenie osobnych sieci Wi-Fi 2,4 i 5GHz dla gości na kontrolerze, seperacja sieci za pośrednictwem vLAN, analiza użycia pasm, sygnału wifi na poszczególnych urządzeniach, przepustowości na AP i urządzeniach końcowych, blokowanie urządzeń.

d. Zapory ogniowe
- Konfiguracja NGFW Sophos XG Firewall Home Edition na Mini PC HP, dołożenie karty sieciowej 4x1Gb, konfiguracja interfejsów i podinterfejsów na potrzeby osobnych vLAN, podział sieci na podsieci, podpięcie licencji, konfiguracja reguł zapory w oparciu o strefy i adresy IP/MAC urządzeń, ograniczenie dostępu do urządzeń sieciowych w vLAN zarządzania tylko dla konkretnych adresów IP, włączenie filtrowania SSL/TLS na urządzeniach, import certyfikatu na urządzeniach końcowych, modyfikacja reguł filtrowania Web i IPS, dodawanie wyjątków na zaporze, analiza blokowanego ruchu w logach urządzenia, czyszczenie dysku urządzenia z starych logów/raportów.
- Wstępna konfiguracja zapory Juniper SSG5 i przegląd funkcji.

2. VPN
- konfiguracja SSL VPN na zaporze Sophos XG Firewall, konfiguracja polityk.
- instalacja i konfiguracja Tailscale VPN na urządzeniach.

3. Serwery plików
- Konfiguracja serwera plików TrueNAS z udziałem SMB (RAIDZ-1) na PC Dell, dołożenie karty sieciowej SFP+ 10Gb, konfiguracja i agregacja interfejsów, tworzenie migawek (snapshotów).

4. Kopie zapasowe i bezpieczeństwo
- Tworzenie kopii zapasowych urządzeń, maszyn wirtualnych.
- Aktualizacja oprogramowania na urządzeniach.
- Instalacja i konfiguracja systemu SIEM Wazuh na Dockerze do wykrywania podatności na urządzeniach końcowych Windows i Linux, analiza i usuwanie podatności.
- Analiza raportów i wykrytych zagrożeń na zaporze Sophos XG Firewall.
  
5. Wirtualizacja i konteneryzacja
- Konfiguracja serwera Proxmox na Mini PC, tworzenie maszyn wirtualnych, i szablonów VM, konfiguracja kopii zapasowych na udział sieciowy SMB (TrueNAS) z użyciem Proxmox Backup Serwer, migracja maszyn wirtualnych na inny serwer Proxmox.

- Maszyny wirtualne na Proxmox: 
+ Windows Desktop - monitorowanie zasilacza UPS CyberPower
+ Linux Ubuntu Desktop - instalacja i konfiguracja kontrolera WLC Unifi
+ Windows Serwer - instalacja i konfiguracja AD, tworzenie kont użytkowników, grup, polityk GPO.

- Kontenery na Dockerze:
+ Instalacja i konfiguracja AdGuardHome, konfiguracja serwera cache DNS i szyfrowania zapytań DNS z użyciem DNSoverTLS, konfiguracja filtrów.
+ Instalacja i konfiguracja kontenerów tj. RustDesk Serwer, Nextterm, Netbox.
+ Instalacja i konfiguracja Uptime Kumy, podłączenie monitorowanych urządzeń, włączenie powiadomień na Discorda.

6. Monitoring i diagnostyka
- Instalacja i konfiguracja serwera Zabbix 6.4 na Linux Serwer, dodanie hostów do monitorowania, podłączanie szablonów, dodawanie nowych czujek i wyzwalaczy alarmów, tworzenie nowych kont użytkowników, grup, integracja z Active Directory na Windows Serwer.
- Instalacja i konfiguracja Grafany, integracja z Zabbix-em.
- Konfiguracja kamer IP Dahua do monitoringu obiektu wraz z wysyłaniem powiadomień na telefon.

7. Bazy danych
- Instalacja i konfiguracja bazy danych MySQL pod serwer Zabbix oraz Apache na Linux Serwer.

8. Dokumentacja
- Tworzenie dokumentacji tradycyjnej oraz z użyciem aplikacji kontenerowej Netbox.

9. Montaż UPS zapewniających zasilanie awaryjne dla krytycznych elementów sieci (serwery, NAS, ruter, przełączniki, zapory ogniowe, punkty dostępowe).
