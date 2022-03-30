---
title: Uaktualnianie do modelu globalnej książki adresowej i strony
description: W tym temacie opisano sposób uaktualniania danych o dwóch zapisach do strony globalna książka adresowa modelu.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 95d272d9076f1ab25230e4efa98e321bdd618062
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407802"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Uaktualnianie do modelu globalnej książki adresowej i strony

[!include [banner](../../includes/banner.md)]



[Szablony Microsoft Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) pomaga zaktualizować następujące istniejące tabele danych **Konto**, **Kontakt** i **Dostawca** za pomocą podwójnego zapisu dla strony i modelu globalnej książki adresowej.

Dostępne są następujące trzy szablony Data Factory. Pomagają uzgadniać dane zarówno z aplikacji Finanse i Operacje, jak i aplikacji do obsługi klienta.

- **[Szablon strony](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Uaktualnij dane do schematu strony-GAB podwójnego zapisu/arm_template.json)** — ten szablon pomaga uaktualnić dane **Strony** i **Kontaktu** skojarzone z danymi **Konta**, **Kontaktu** i **Dostawcy**.
- **[Szablon adresu pocztowego strony](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Uaktualnij dane do schematu podwójnego zapisu strony-GAB/Uaktualnij do adresu pocztowego strony — GAB/arm_template.json)** — ten szablon ułatwia uaktualnienie adresów pocztowych skojarzonych z danymi **Konta**, **Kontaktu** i **Dostawcy**.
- **[Szablon adresu poczty elektronicznej strony](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Uaktualnij dane do schematu podwójnego zapisu strony-GAB/Uaktualnij do adresu poczty elektronicznej strony — GAB/arm_template.json)** — ten szablon ułatwia uaktualnienie adresów poczty elektronicznej skojarzonych z danymi **Konta**, **Kontaktu** i **Dostawcy**.

Po zakończeniu procesu generowane są następujące pliki z wartościami rozdzielanymi przecinkami (csv).

| Nazwa pliku | Cel |
|---|---|
| FONewParty.csv | Ten plik pomaga tworzyć nowe rekordy **Jednostka** w aplikacji Finanse i Operacje. |
| ImportFONewPostalAddressLocation.csv | Ten plik pomaga w tworzeniu nowych rekordów **Lokalizacji adresu pocztowego** w aplikacji Finanse i Operacje. |
| ImportFONewPartyPostalAddress.csv | Ten plik pomaga w tworzeniu nowych rekordów **Lokalizacji adresu pocztowego** w aplikacji Finanse i Operacje. |
| ImportFONewPostalAddress.csv | Ten plik pomaga w tworzeniu nowych rekordów **Adres pocztowy** w aplikacji Finanse i Operacje. |
| ImportFONewElectronicAddress.csv | Ten plik pomaga w tworzeniu nowych rekordów **Adres elektroniczny** w aplikacji Finanse i Operacje. |

Ten temat wyjaśnia instrukcje dotyczące używania szablonów Data Factory i uaktualniania danych. Jeśli nie masz żadnych dostosowań, możesz użyć szablonów w takiej postaci, w jakiej są. Jeśli jednakże masz dostosowania dla danych **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablony, tak jak opisano w tym temacie.

> [!IMPORTANT]
> Jeśli będą uruchamiane szablony adresów pocztowych i adresów poczty elektronicznej stron, istnieją specjalne instrukcje. Najpierw należy uruchomić szablon strony, następnie szablon adresu pocztowego strony, a na końcu szablon adresu poczty elektronicznej strony. Każdy szablon jest przeznaczony do importowania w osobnej fabryki danych.

## <a name="prerequisites"></a>Wymagania wstępne

Do uaktualnienia do modelu strony i globalnej książki adresowej wymagane są następujące warunki wstępne:

+ Musisz mieć [subskrypcję systemu Azure](https://portal.azure.com/).
+ Trzeba mieć dostęp do [szablonów](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Musisz być istniejącym klientem podwójnego zapisu.

## <a name="prepare-for-the-upgrade"></a>Przygotowanie do aktualizacji

Uaktualnienie wymaga następującego przygotowania:

+ **Pełna synchronizacja:** środowisko Finanse i Działania oraz środowisko Customer Engagement są w pełni zsynchronizowane dla tabel **Konto (Odbiorca**), **Kontakt** i **Dostawca**.
+ **Klucze integracji:** tabele **konto (Klient)**, **Kontakt** i **Dostawca** w aplikacjach zaangażowania klienta są dostępne za pomocą gotowych kluczy integracji. Jeśli użytkownik dostosuje klucze integracji, należy dostosować szablon.
+ **Numer strony:** Wszystkie rekordy **Konto (Klient)**, **Kontakt** i **Dostawca**, które zostaną zaktualizowane, mają numer strony. Rekordy, które nie mają numeru strony, zostaną zignorowane. Aby uaktualnić te rekordy, dodaj do nich numer strony przed rozpoczęciem procesu uaktualniania.
+ **Okres przestoju systemu:** Podczas procesu uaktualniania konieczne będzie przełączenie środowisk Finanse i Działania oraz zaangażowania klienta do trybu offline.
+ **Migawka**: tworzenie migawki aplikacji Finanse i Operacje i aplikacji obsługi klienta. W razie konieczności użyj migawki, aby przywrócić poprzedni stan.

## <a name="deployment"></a>Wdrażanie

1. Pobierz szablony z witryny [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/).
3. Wybierz [grupę zasobów](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Utwórz [konto magazynu](/azure/storage/common/storage-account-create?tabs=azure-portal) w utworzonej grupie zasobów.
5. Utwórz [fabryke danych](/azure/data-factory/quickstart-create-data-factory-portal) w utworzonej grupie zasobów.
6. Otwórz fabrykę danych i wybierz kafelek **Twórz i Monitoruj**.
7. Na karcie **Zarządzaj** wybierz **Szablon ARM**.
8. Wybierz **Importuj szablon ARM**, aby zaimportować szablon **Strony**.
9. Importowanie szablonu do fabryki danych. Wprowadź następujące wartości **Szczegółów projektu** i **Szczegółów wystąpienia**.

    | Pole | Wartość |
    |---|---|
    | Subskrypcja | Subskrypcja platformy Azure |
    | Grupa zasobów | Podaj ten sam zasób, pod którym zostanie utworzone konto magazynu. |
    | Region | Region |
    | Nazwa fabryki | Nazwa fabryki |
    | FO Powiązanego klucza głównego Service_service | Klucz aplikacji |
    | Ciąg Azure Blob Storage_connection | Parametry połączenia magazynu Azure Blob Storage |
    | Hasło usługi powiązane z Dynamics Crm | Hasło do konta użytkownika określonego jako nazwa użytkownika |
    | FO Połączone Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO Połączone Service_properties_type Properties_tenant | Informacje o dzierżawcy (nazwa domeny lub identyfikator dzierżawcy), pod którymi znajduje się aplikacja |
    | FO Połączone Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO Połączone Service_properties_type Properties_service Principal Id | Identyfikator klienta aplikacji |
    | Dynamics Crm Linked Service_properties_type Properties_username | Nazwa użytkownika używana do połączenia z Dynamics 365 |

    Aby uzyskać więcej informacji, zobacz następujące tematy:

    - [Ręczne promowanie szablonu Resource Manager dla każdego środowiska](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Połączone właściwości usługi](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Kopiowanie danych przy użyciu Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Po wdrożeniu sprawdź poprawność zestawów danych, przepływu danych i połączonej usługi fabryki danych.

    ![Zestawy danych, przepływ danych i połączona usługa.](media/data-factory-validate.png)

11. Przejdź do **Zarządzaj**. W obszarze **Połączenia** wybierz pozycję **Połączona usługa**. Następnie wybierz **DynamicsCrmLinkedService**. W okienku dialogowym **Edycja połączonej usługi (Dynamics CRM)** wprowadź następujące wartości.

    | Pole | Wartość |
    |---|---|
    | Nazwa | DynamicsCrmLinkedService |
    | opis | Połączone usługi nawiązania połączenia z wystąpieniem CRM w celu pobrania danych jednostek |
    | Połącz za pomocą środowiska uruchomieniowego integracji | AutoResolvelntegrationRuntime |
    | Typ wdrożenia | Online |
    | URI usługi | `https://<organization-name>.crm[x].dynamics.com` |
    | Typ uwierzytelniania | Office365 |
    | Nazwa użytkownika | |
    | Hasło lub klucz Azure | Hasło |
    | Hasło | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Przygotuj do uruchomienia szablonów Data Factory

W tej sekcji opisano ustawienia wymagane przed uruchomieniem szablonów adresów pocztowych i szablonów Data Factory adresów poczty elektronicznej stron.

### <a name="setup-to-run-the-party-postal-address-template"></a>Konfiguracja uruchamiania szablonu adresu pocztowego strony

1. Zaloguj się do aplikacji zaangażowania klienta i przejdź do **Ustawienia** \> **Personalizacja ustawień**. Następnie na karcie **Ogólne** skonfiguruj ustawienie strefy czasowej dla konta administratora systemu. Aby można było zaktualizować daty „ważny od” i „ważny do” adresów pocztowych w aplikacjach Finanse i Operacje, strefa czasowa musi być w uniwersalnym czasie koordynowanym (UTC).

    ![Ustawienie strefy czasowej dla konta administratora systemu.](media/ADF-1.png)

2. W Data Factory na karcie **Zarządzaj**, w obszarze **Parametry globalne** utwórz następujący parametr globalny.

    | Identyfikator | Nazwa | Typ | Wartość |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | ciąg | Ten parametr dołącza numer seryjny do nowo utworzonych adresów pocztowych jako prefiks. Pamiętaj, aby podać ciąg, który nie koliduje z adresami pocztowymi w aplikacjach Finanse i Operacje i aplikacjach zaangażowania klienta. Na przykład użyj **ADF-PAD-**. |

    ![Parametr globalny PostalAddressIdPrefix utworzony na karcie Zarządzaj.](media/ADF-2.png)

3. Po zakończeniu wybierz przycisk **Publikuj wszystko**.

    ![Przycisk Publikuj wszystko.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>Konfiguracja uruchamiania szablonu adresu poczty elektronicznej strony

1. W Data Factory na karcie **Zarządzaj**, w obszarze **Parametry globalne** utwórz następujące parametry globalne.

    | Identyfikator | Nazwa | Typ | Wartość |
    |---|---|---|---|
    | 1 | IsFOSource | bool | Ten parametr określa, które główne adresy systemowe są zastępowane w razie konfliktów. Jeśli ta wartość jest **Prawda**, adresy podstawowe w aplikacjach Finanse i Operacje zastąpią adresy podstawowe w aplikacjach zaangażowania klienta. Jeśli ta wartość jest **Fałsz**, adresy podstawowe w aplikacjach zaangażowania klienta zastąpią adresy podstawowe w aplikacjach Finanse i Operacje. |
    | 2 | ElectronicAddressIdPrefix | ciąg | Ten parametr dołącza numer seryjny do nowo utworzonych adresów poczty elektronicznej jako prefiks. Pamiętaj, aby podać ciąg, który nie koliduje z adresami elektronicznymi w aplikacjach Finanse i Operacje i aplikacjach zaangażowania klienta. Na przykład użyj **ADF-EAD-**. |

    ![Parametry globalne IsFOSource i ElectronicAddressIdPrefix utworzone na karcie Zarządzaj.](media/ADF-4.png)

2. Po zakończeniu wybierz przycisk **Publikuj wszystko**.

## <a name="run-the-templates"></a>Uruchom szablony

1. Zatrzymaj mapowania podwójnego zapisu **Strona**, **Konto**, **Kontakt** i **Dostawca** używające aplikacji finansowych i operacyjnych:

    + Strony CDS (msdyn_parties) 
    + Odbiorcy wersja 3 (konta)
    + Odbiorcy wersja 3(kontakty)
    + CDS Kontakty V2(kontakty)
    + CDS Kontakty V2(kontakty)
    + Dostawca wersja 2 (msdyn_vendor)
    + Kontakty V2 (msdyn_contactforparties)
    + Lokalizacje adresów pocztowych stron CDS (msdyn_partypostaladdresses)
    + Historia adresów pocztowych CDS w wersji 2 (msdyn_postaladdresses)
    + Lokalizacje adresów pocztowych CDS (msdyn_postaladdresscollections)
    + Kontakty strony V3 (msdyn_partyelectronicaddresses)

2. Upewnij się, że mapy zostały usunięte z tabeli **msdy_dualwriteruntimeconfig** w danych Dataverse.
3. Zainstaluj [Rozwiązania z podwójnym zapisem i globalna książka adresowa](https://aka.ms/dual-write-gab) z AppSource.
4. W aplikacji Finanse i Operacje uruchom dla nich **wstępną synchronizację**, jeśli poniższe tabele zawierają dane.

    + Zwroty grzecznościowe
    + Typy osób
    + Formuła grzecznościowa
    + Tytuły osoby kontaktowej
    + Role podejmujące decyzje
    + Poziomy lojalności

5. W aplikacji obsługi klienta wyłącz poniższe kroki dodatku plug-in:

    + Aktualizacja konta

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aktualizacja konta
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aktualizacja konta

    + Aktualizacja kontaktu

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aktualizacja kontaktu
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aktualizacja kontaktu

    + msdyn_party aktualizacja

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aktualizacja msdyn_party

    + msdyn_vendor aktualizacja

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aktualizacja msdyn_vendor

    + Customeraddress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: tworzenie customeraddress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: aktualizacja customeraddress

        + Usuń

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: usuwanie customeraddress

    + msdyn_partypostaladdress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: tworzenie msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: tworzenie msdyn_partypostaladdress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: aktualizacja msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: aktualizacja msdyn_partypostaladdress

    + msdyn_postaladdress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: tworzenie msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: tworzenie msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: tworzenie msdyn_postaladdress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: aktualizacja msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: aktualizacja msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: tworzenie msdyn_partyelectronicaddress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: aktualizacja msdyn_partyelectronicaddress

        + Usuń

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: usuwanie msdyn_partyelectronicaddress

6. W aplikacji obsługi klienta wyłącz poniższe przepływy pracy:

    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców typu osoba w tabeli kontaktów
    + Tworzenie dostawców typu Osoba w tabeli dostawców
    + Aktualizowanie dostawców w tabeli kont
    + Aktualizowanie dostawców w tabeli dostawców
    + Aktualizowanie dostawców typu Osoba w tabeli kontaktów
    + Aktualizowanie dostawców typu Osoba w tabeli dostawców

7. W fabryki danych uruchom szablon, wybierając pozycję **Wyzwól teraz**, tak jak pokazano na poniższej ilustracji. Zakończenie tego procesu może potrwać kilka godzin w zależności od objętości danych.

    ![Uruchomienie szablonu](media/data-factory-trigger.png)

    > [!NOTE]
    > Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon.

8. Zaimportuj nowe rekordy **Strony** do aplikacji Finanse i Operacje.

    1. Pobierz plik **FONewParty.csv** z magazynu obiektów blob Azure Blob Storage. Ścieżką jest **partybootstrapping/output/FONewParty.csv**.
    2. Skonwertuj plik **FONewParty.csv** na plik programu Excel i zaimportuj go do aplikacji Finanse i Operacje. Alternatywnie, jeśli import CSV jest odpowiedni dla użytkownika, można zaimportować plik CSV bezpośrednio. Zakończenie tego kroku może potrwać kilka godzin w zależności od objętości danych. Aby uzyskać więcej informacji, zapoznaj się z [Omówieniem importowania i eksportowania danych](../data-import-export-job.md).

    ![Importowanie rekordów strony Dataverse.](media/data-factory-import-party.png)

9. W fabryce danych uruchom szablony adresu pocztowego strony i adresu poczty elektronicznej strony, jeden po drugim.

    + Szablon adresu pocztowego strony jest odpowiednio uwzględniany w wszystkich rekordach adresów pocztowych w aplikacji zaangażowania klienta i kojarzy je z odpowiednimi rekordami **Konto**, **Kontakt** i **Dostawca**. Ponadto są generowane trzy pliki .csv: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv i ImportFONewPostalAddress.csv.
    + Szablon adresu poczty elektronicznej strony jest odpowiednio uwzględniany w wszystkich rekordach adresów poczty elektronicznej w aplikacji zaangażowania klienta i kojarzy je z odpowiednimi rekordami **Konto**, **Kontakt** i **Dostawca**. Zostanie również wygenerowany jeden plik csv: ImportFONewElectronicAddress.csv.

    ![Uruchamianie szablonów adresów pocztowych i adresów poczty elektronicznej stron.](media/ADF-7.png)

10. Aby zaktualizować aplikację Finanse i Operacje przy użyciu tych danych, należy przekonwertować pliki CSV na skoroszyt programu Excel i [zaimportować je do aplikacji Finanse i Operacje](/data-entities/data-import-export-job). Alternatywnie, jeśli import CSV jest odpowiedni dla użytkownika, można zaimportować pliki CSV bezpośrednio. Zakończenie tego kroku może potrwać kilka godzin w zależności od objętości danych.

    ![Pomyślne zaimportowanie.](media/ADF-8.png)

11. W aplikacji zaangażowania klienta włącz następujące kroki wtyczki:

    + Aktualizacja konta

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aktualizacja konta
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aktualizacja konta

    + Aktualizacja kontaktu

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aktualizacja kontaktu
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aktualizacja kontaktu

    + msdyn_party aktualizacja

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aktualizacja msdyn_party

    + msdyn_vendor aktualizacja

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aktualizacja msdyn_vendor

    + msdyn_partypostaladdress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: tworzenie msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: tworzenie msdyn_partypostaladdress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: aktualizacja msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: aktualizacja msdyn_partypostaladdress

    + msdyn_postaladdress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: tworzenie msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: tworzenie msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: tworzenie msdyn_postaladdress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: aktualizacja msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: aktualizacja msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Utwórz

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: tworzenie msdyn_partyelectronicaddress

        + Aktualizuj

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: aktualizacja msdyn_partyelectronicaddress

        + Usuń

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: usuwanie msdyn_partyelectronicaddress

12. W aplikacji zaangażowania klienta aktywuj następujące przepływy pracy, jeśli wcześniej je zdezaktywowano:

    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców typu osoba w tabeli kontaktów
    + Tworzenie dostawców typu Osoba w tabeli dostawców
    + Aktualizowanie dostawców w tabeli kont
    + Aktualizowanie dostawców w tabeli dostawców
    + Aktualizowanie dostawców typu Osoba w tabeli kontaktów
    + Aktualizowanie dostawców typu Osoba w tabeli dostawców

13. Uruchom mapy powiązane z rekordem **Strona**, jak opisano w [Książka adresowa strony i globalna książka adresowa](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Objaśnienie szablonów Data Factory

W tej sekcji możesz przejść przez kolejne kroki w każdym szablonie Data Factory.

### <a name="steps-in-the-party-template"></a>Kroki w szablonie strony

1. Kroki od 1 do 6 identyfikują firmy, dla których włączono obsługę podwójnego zapisu i tworzy dla nich klauzulę filtru.
2. Kroki od 7–1 do 7–9 pobierają dane z aplikacji Finanse i Operacje i aplikacji zaangażowania klienta, a następnie etap, w których dane są uaktualnianie.
3. Kroki od 8 do 9 porównują numer strony dla rekordów **Konto**, **Kontakt** i **Dostawca** między aplikacją Finanse i Operacje a aplikacją zaangażowania klienta. Wszelkie rekordy, które nie mają numeru strony, zostaną pominięte.
4. Krok 10 generuje dwa pliki csv dla rekordów stron, które muszą zostać utworzone w aplikacji zaangażowania klienta i aplikacji Finanse i Operacje.

    - **FOCDSParty.csv** — ten plik zawiera wszystkie rekordy stron w obu systemach, niezależnie od tego, czy w firmie włączono obsługę podwójnego zapisu.
    - **FONewParty.csv** — ten plik zawiera podzestaw rekordów stron, na które zwraca uwagę Dataverse (na przykład konta typu **Prospekt**).

5. Krok 11 tworzy strony w aplikacji zaangażowania klienta.
6. Krok 12 umożliwia pobranie unikatowych identyfikatorów globalnych (GUID) stron z aplikacji zaangażowania klienta oraz ich etapy, dzięki czemu można je skojarzyć z rekordami **Konto**, **Kontakt** i **Dostawca** w kolejnych krokach.
7. Krok 13 kojarzy rekordy **Konto**, **Kontakt** i **Dostawca** z identyfikatorami GUID strony.
8. Kroki od 14–1 do 14–3 aktualizują rekordy **Konto**, **Kontakt** i **Dostawca** w aplikacji zaangażowania klienta przy użyciu identyfikatorów GUID stron.
9. Kroki od 15–1 do 15–3 przygotowują rekordy **Osoba kontaktowa dla strony** dla rekordów: **Konto**, **Kontakt** i **Dostawca**.
10. Kroki od 16–1 do 16–7 pobierają dane referencyjne, takie jak zwroty grzecznościowe i typy osób, i kojarzą je z rekordami **Osoba kontaktowa dla strony**.
11. Krok 17 scala rekordy **Osoba kontaktowa dla strony** dla rekordów **Konto**, **Kontakt** i **Dostawca**.
12. Krok 18 importuje rekordy **Osoba kontaktowa dla strony** do aplikacji zaangażowania klienta.

### <a name="steps-in-the-party-postal-address-template"></a>Kroki w szablonie adresu pocztowego strony

1. Kroki od 1–1 do 1–10 pobierają dane z aplikacji Finanse i Operacje i aplikacji zaangażowania klienta, a następnie etap, w których dane są uaktualnianie.
2. Krok 2 usuwa normalizację danych adresu pocztowego w aplikacji Finanse i Operacje, przyłączając adres pocztowy i adres pocztowy strony.
3. Krok 3 usuwa duplikowanie i scala dane konta, kontaktów i adresów dostawców z aplikacji zaangażowania klientów.
4. Krok 4 powoduje utworzenie plików csv dla aplikacji Finanse i Operacje w celu utworzenia nowych danych adresowych opartych na adresach kont, kontaktów i dostawców.
5. Krok 5–1 tworzy pliki csv dla aplikacji zaangażowania klienta, aby tworzyć wszystkie dane adresowe na podstawie aplikacji Finanse i Operacje i aplikacji zaangażowania klienta.
6. Krok 5–2 konwertuje pliki .csv do formatu importu aplikacji Finanse i Operacje w celu ręcznego importowania.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. Krok 6 importuje dane kolekcji adresów pocztowych do aplikacji zaangażowania klienta.
8. Krok 7 pobiera dane kolekcji adresów pocztowych z aplikacji zaangażowania klienta.
9. Krok 8 tworzy dane adresowe odbiorcy i kojarzy identyfikator kolekcji adresów pocztowych.
10. Kroki od 9–1 do 9–2 kojarzą identyfikatory kolekcji stron i adresów pocztowych z adresami pocztowymi i adresami pocztowymi stron.
11. Kroki od 10–1 do 10–3 importują adresy odbiorców, adresy pocztowe i adresy pocztowe stron do aplikacji zaangażowania klienta.

### <a name="steps-in-the-party-electronic-address-template"></a>Kroki w szablonie adresu poczty elektronicznej strony

1. Kroki od 1–1 do 1–5 pobierają dane z aplikacji Finanse i Operacje i aplikacji zaangażowania klienta, a następnie etap, w których dane są uaktualnianie.
2. Krok 2 konsoliduje adresy poczty elektronicznej w aplikacji zaangażowania klienta z jednostek Konto, Osoba kontaktowa i Dostawca.
3. Krok 3 scala podstawowe dane adresu poczty elektronicznej z aplikacji zaangażowania klienta i aplikacji Finanse i Operacje.
4. Krok 4 powoduje utworzenie plików csv.

    - Utwórz nowe dane adresu poczty elektronicznej dla aplikacji Finanse i Operacje na podstawie adresów kont, kontaktów i dostawców.
    - Utwórz nowe dane adresu poczty elektronicznej w aplikacji zaangażowania klienta, oparte na adresie poczty elektronicznej, koncie, adresie kontaktowym i adresie dostawcy w aplikacji Finanse i Operacje.

5. Krok 5–1 umożliwia import adresów poczty elektronicznej do aplikacji zaangażowania klienta.
6. Krok 5–2 powoduje utworzenie plików .csv w celu zaktualizowania adresów podstawowych dla kont i kontaktów w aplikacji zaangażowania klienta.
7. Kroki od 6–1 do 6–2 importują konta i kontakty z adresami podstawowymi w aplikacji zaangażowania klienta.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

1. Jeśli proces nie powiedzie się, należy ponownie uruchomić fabrykę danych. Rozpocznij od działania, które zakończyło się niepowodzeniem.
2. Niektóre pliki, które są generowane przez fabryki danych, mogą być użyte do walidacji.
3. Fabryki danych są uruchamiane na podstawie plików CSV. Jeśli zatem przecinek jest uwzględniony w którejkolwiek wartości pola, może zakłócać wyniki. Musisz usunąć wszystkie przecinki z wartości pól.
4. Karta **Monitorowanie** zawiera informacje o wszystkich krokach i danych, które zostały przetworzone. Wybierz określony krok do debugowania.

    ![Karta Monitorowanie.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Dowiedz się więcej o szablonie

Więcej informacji dotyczących tego szablonu można znaleźć w sekcji [Pliku Readme —Komentarze do Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
