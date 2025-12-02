# Home IT Lab – Enterprise Environment

Symulacja dużego środowiska informatycznego klasy enterprise 

**Cel laboratorium**  
Przygotowanie do konkursu  na stanowisko Administratora Systemu Informatycznego w Sądzie Apelacyjnym we Wrocławiu.

## Architektura (stan na 02.12.2025)

| Komponent                | Technologia                        | Wersja            | Status
|---|---|---|---|
| Hypervisor               | 3× VMware ESXi (nested)            | 8.0 Update 3      | Działa
| Zarządzanie              | vCenter Server Appliance           | 8.0 U3            | Działa
| Sieć wirtualna           | vSphere Distributed Switch (vDS)   | –                 | Działa
| Storage                  | TrueNAS SCALE → iSCSI              | najnowsza         | Działa
| Usługi katalogowe        | 2× Windows Server 2022 DC          | 2022              | Działa (replika)
| Klient testowy           | Windows 10 LTSC 2021               | 21H2              | Dołączony do domeny
| Wirtualizacja Microsoft  | Hyper-V (nested)                   | 2022              | Wdrożenie w toku
| Linux                    | AlmaLinux 9.4 (RHEL 9 clone)       | 9.4               | Wdrożenie w toku
| Monitorowanie            | Zabbix 6.4/7.0                     | –                 | Planowane

## Co już działa (grudzień 2025)
- VMware vSphere 8 z pełnym vCenter (vDS + live vMotion + iSCSI)
- Active Directory – dwa kontrolery domeny z replikacją FSMO i SYSVOL
- Klient Windows 10 przyłączony do domeny
- Wszystkie elementy uruchomione na VMware Workstation Pro 15H2 (64 GB RAM, Xeon E5-2683 v4)

Repozytorium będzie rozwijane do 15.12.2025 – kolejne elementy (Hyper-V, AlmaLinux, Zabbix, przykłady incydentów i napraw) pojawią się w najbliższych dniach.

→ szczegóły w folderach `/screenshots` oraz `/scripts`
