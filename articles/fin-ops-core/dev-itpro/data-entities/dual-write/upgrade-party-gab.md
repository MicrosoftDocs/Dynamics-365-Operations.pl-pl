---
title: Uaktualnianie do modelu globalnej książki adresowej i strony
description: W tym temacie opisano sposób uaktualniania danych o dwóch zapisach do strony globalna książka adresowa modelu.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 673c3a68e2eccdabdfc2df281389537297ec3524bee5e744e910c50d38b8d298
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720695"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Uaktualnianie do modelu globalnej książki adresowej i strony

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[Szablon Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) pomaga zaktualizować istniejące tabele danych **Konto**, **Kontakt** i **Dostawca** za pomocą podwójnego zapisu dla strony i modelu globalnej książki adresowej. Szablon uzgadnia dane z aplikacji Finance and Operations oraz aplikacji angażujących klientów. Na zakończenie procesu zostaną utworzone i skojarzone pola **Strona** i **Kontakt** dla rekordów **Strony** z rekordami **Konto**, **Kontakt** i **Dostawca** w aplikacjach zaangażowania kllienta. Zostanie wygenerowany plik csv (`FONewParty.csv`) w celu utworzenia nowych rekordów **Strona** w aplikacji Finance and Operations. Ten temat zawiera instrukcje dotyczące używania szablonu Data Factory i uaktualniania danych.

Jeśli nie masz żadnych dostosowań, możesz użyć szablonu w takiej postaci, w jakiej jest. Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon, korzystając z poniższych instrukcji.

> [!NOTE]
> Szablon uaktualnia tylko dane **Strony**. W przyszłej wersji zostaną uwzględnione adresy pocztowe i elektroniczne.

## <a name="prerequisites"></a>Wymagania wstępne

Do uaktualnienia do modelu imprez i globalnej książki adresowej wymagane są następujące warunki wstępne:

+ [Subskrypcja platformy Azure](https://portal.azure.com/)
+ [Dostęp do szablonu](https://aka.ms/dual-write-gab-adf)
+ Musisz być istniejącym klientem podwójnego zapisu.

## <a name="prepare-for-the-upgrade"></a>Przygotowanie do aktualizacji
Aby przygotować się do aktualizacji, należy wykonać następujące czynności:

+ **W pełni zsynchronizowane**: oba środowiska są w pełni zsynchronizowane dla **Konto (klient)**, **Kontakt** i **Dostawca**.
+ **Klucze integracji**: tabele **konto (Klient)**, **Kontakt** i **Dostawca** w aplikacjach do obsługi klienta są dostępne za pomocą kluczy integracji, które są gotowe do użytku. Jeśli użytkownik dostosuje klucze integracji, należy dostosować szablon.
+ **Numer strony**: Wszystkie rekody **Konto (Klient)**, **Kontakt** i **Dostawca**, które zostaną zaktualizowane, mają numer **Strony**. Rekordy bez numeru **Strony** zostaną zignorowane. Aby uaktualnić te rekordy, dodaj do nich numer **Strony** przed rozpoczęciem procesu uaktualniania.
+ **Okres przestoju systemu**: Podczas procesu uaktualniania konieczne będzie przełączenie środowisk Finance and Operations oraz obsługi klienta do trybu offline.
+ **Migawka**: tworzenie migawki aplikacji Finance and Operations i aplikacji obsługi klienta. W razie potrzeby użyj migawki, aby przywrócić poprzedni stan.

## <a name="deployment"></a>Wdrażanie

1. Pobierz szablon z witryny [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).

2. Zaloguj się w [Microsoft Azure](https://portal.azure.com/).

3. Wybierz [grupę zasobów](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Utwórz [konto magazynu](/azure/storage/common/storage-account-create?tabs=azure-portal) w utworzonej grupie zasobów.

5. Utwórz [fabryke danych](/azure/data-factory/quickstart-create-data-factory-portal) w utworzonej powyżej grupie zasobów.

6. Otwórz fabrykę danych i wybierz kafelek **Twórz i Monitoruj**.

7. Na karcie **Zarządzaj** wybierz **Szablon ARM**.

8. Wybierz **Importuj szablon ARM**, aby zaimportować szablon **Strony**.

9. Importowanie szablonu do fabryki danych. Wprowadź następujące wartości **Szczegółów projektu** i **Szczegółów wystąpienia**.

    Pole | Wartość
    ---|---
    Subskrypcja | Subskrypcja platformy Azure
    Grupa zasobów | Podaj ten sam zasób, pod którym zostanie utworzone konto magazynu.
    Region | Określ region.
    Nazwa fabryki | Określ nazwę fabryki.
    FO Powiązanego klucza głównego Service_service | Określ klucz aplikacji.
    Ciąg Azure Blob Storage_connection | Parametry połączenia usługi Azure Blob Storage.
    Hasło usługi powiązane z Dynamics Crm | Hasło do konta użytkownika określonego jako nazwa użytkownika.
    FO Połączone Service_properties_type Properties_url  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    FO Połączone Service_properties_type Properties_tenant | Określ informacje o dzierżawcy (nazwę domeny lub identyfikator dzierżawy), pod którymi znajduje się aplikacja.
    FO Połączone Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com`
    FO Połączone Service_properties_type Properties_service Principal Id | Określ identyfikator klienta aplikacji.
    Dynamics Crm Linked Service_properties_type Properties_username | Nazwa użytkownika do połączenia z Dynamics 365.

    Aby uzyskać więcej informacji, zobacz następujące tematy: 
    
    - [Ręczne promowanie szablonu Resource Manager dla każdego środowiska](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Połączone właściwości usługi](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Kopiowanie danych przy użyciu Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Po wdrożeniu sprawdź poprawność zestawów danych, przepływu danych i połączonej usługi fabryki danych.

   ![Zestawy danych, przepływ danych i połączona usługa.](media/data-factory-validate.png)

11. Przejdź do **Zarządzaj**. W obszarze **Połączenia** wybierz pozycję **Połączona usługa**. Wybierz **DynamicsCrmLinkedService**. W formularzu **Edycja połączonej usługi (Dynamics CRM)** wprowadź następujące wartości.

    Pole | Wartość
    ---|---
    Imię i nazwisko | DynamicsCrmLinkedService
    opis | Połączone usługi nawiązania połączenia z wystąpieniem CRM w celu pobrania danych jednostek
    Połącz za pomocą środowiska uruchomieniowego integracji | AutoResolvelntegrationRuntime
    Typ wdrożenia | Online
    URI usługi | `https://<organization-name>.crm[x].dynamics.com`
    Typ uwierzytelniania | Office365
    Nazwa użytkownika |
    Hasło lub klucz Azure | Hasło
    Hasło |

## <a name="run-the-template"></a>Uruchom szablon.

1. Zatrzymaj korzystanie z mapowania podwójnego zapisu **Konto**, **Kontakt** i **Dostawca** za pomocą aplikacji Finance and Operations.

    + Odbiorcy wersja 3 (konta)
    + Odbiorcy wersja 3(kontakty)
    + CDS Kontakty V2(kontakty)
    + CDS Kontakty V2(kontakty)
    + Dostawca wersja 2 (msdyn_vendor)

2. Upewnij się, że mapy zostały usunięte z tabeli `msdy_dualwriteruntimeconfig` w Dataverse.

3. Zainstaluj [Rozwiązania z podwójnym zapisem i globalna książka adresowa](https://aka.ms/dual-write-gab) z AppSource.

4. W aplikacji Finance and Operations, jeśli poniższe tabele zawierają dane, uruchom dla nich **wstępną synchronizację**.

    + Zwroty grzecznościowe
    + Typy osób
    + Formuła grzecznościowa
    + Tytuły osoby kontaktowej
    + Role podejmujące decyzje
    + Poziomy lojalności

5. W aplikacji obsługi klienta wyłącz poniższe kroki dodatku plug-in.

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

6. W aplikacji obsługi klienta wyłącz poniższe przepływy pracy:

    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców typu osoba w tabeli kontaktów
    + Tworzenie dostawców typu Osoba w tabeli dostawców
    + Aktualizowanie dostawców w tabeli kont
    + Aktualizowanie dostawców w tabeli dostawców
    + Aktualizowanie dostawców typu Osoba w tabeli kontaktów
    + Aktualizowanie dostawców typu Osoba w tabeli dostawców

7. W fabryki danych uruchom szablon, wybierając pozycję **Wyzwól teraz**, tak jak pokazano na poniższym obrazie. Ten proces może potrwać kilka godzin na podstawie objętości danych.

    ![Wyzwalanie uruchomienia.](media/data-factory-trigger.png)

    > [!NOTE]
    > Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon.

8. Zaimportuj nowe rekordy **Strony** w aplikacji Finance and Operations.

    + Pobierz plik `FONewParty.csv` z magazynu obiektów blob Azure. Ścieżka w `partybootstrapping/output/FONewParty.csv`.
    + Skonwertuj plik `FONewParty.csv` na plik programu Excel i zaimportuj go do aplikacji Finance and Operations. Jeśli import CSV działa dla Ciebie, możesz zaimportować plik CSV bezpośrednio. Uruchomienie importowania może potrwać kilka godzin, w zależności od objętości danych. Aby uzyskać więcej informacji, zapoznaj się z [Omówieniem importowania i eksportowania danych](../data-import-export-job.md).

    ![Importowanie rekordów strony Dataverse.](media/data-factory-import-party.png)

9. W aplikacjach angażujących klientów włącz następujące kroki wtyczki plug-in:

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

10. W aplikacjach do obsługi klienta aktywuj następujące przepływy pracy, jeśli zdezaktywowano je w poprzednich krokach:

    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców w tabeli kont
    + Tworzenie dostawców typu osoba w tabeli kontaktów
    + Tworzenie dostawców typu Osoba w tabeli dostawców
    + Aktualizowanie dostawców w tabeli kont
    + Aktualizowanie dostawców w tabeli dostawców
    + Aktualizowanie dostawców typu Osoba w tabeli kontaktów
    + Aktualizowanie dostawców typu Osoba w tabeli dostawców

11. Uruchom mapy powiązane z **Stroną** zgodnie z instrukcjami w [Książka adresowa strony i globalna książka adresowa](party-gab.md).

## <a name="troubleshooting"></a>Rozwiązywanie problemów

1. W przypadku niepowodzenia procesu należy ponownie uruchomić fabryki danych począwszy od nieudanych działań.
2. Niektóre pliki są generowane przez fabryki danych, których można używać do weryfikacji danych.
3. Fabryki danych są uruchamiane na podstawie plików CSV, które są rozdzielane przecinkami. Jeśli istnieje wartość pola z przecinkiem, może to wpływać na wyniki. Należy usunąć przecinek.
4. Karta **Monitorowanie** zawiera informacje o wszystkich przetwarzanych krokach i danych. Wybierz określony krok do debugowania.

    ![Karta Monitorowanie.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Dowiedz się więcej o szablonie

Dodatkowe informacje dotyczące tego szablonu można znaleźć w sekcji [Pliku Readme —Komentarze do Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
