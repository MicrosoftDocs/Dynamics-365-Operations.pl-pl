---
title: Deklaracja VAT z ewidencjami (JPK_V7M, VDEK)
description: Ten temat przedstawia proces konfigurowania deklaracji VAT z ewidencjami (zwanej także JPK_V7M, VDEK) w Polsce.
author: liza-golub
ms.date: 11/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Poland
ms.author: elgolu
ms.openlocfilehash: 29a8e1812e89df40968afd751fbb989155217d1f
ms.sourcegitcommit: ec78608eb96478b7a57928b60aece129d6799c5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "4581957"
---
# <a name="vat-declaration-with-registers-jpk_v7m-vdek"></a>Deklaracja VAT z ewidencjami (JPK_V7M, VDEK)

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować deklarację podatku VAT z ewidencjami (zwanymi także JPK_V7M, VDEK) w Polsce.

Od 1 października 2020 firmy w Polsce są zobowiązane do raportowania podatku VAT w dokumencie elektronicznym, który składa się z jednolitego pliku kontrolnego VAT (JPK_VAT) razem z deklaracją (jednolity plik kontrolny VDEK). Żądany dokument elektroniczny zawiera następujące informacje:

- Oba rekordy VAT (zestawienie informacji o zakupach i sprzedaży, które są generowane z rekordów VAT przedsiębiorcy za dany okres)
- Deklaracja VAT (Deklaracja VAT-7)

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można przygotować Microsoft Dynamics 365 Finance do raportowania JPK_V7M, procesy biznesowe i system muszą spełniać następujące warunki:

- Na stronie **Urzędy skarbowe** (**Podatek** > **Podatek pośredni** > **Podatek** > **Urzędy skarbowe**), dla urzędu skarbowego, który jest skojarzony z kodami podatku używanymi w transakcjach podatkowych, które muszą być uwzględnione w raporcie JPK_V7M, pole **Układ raportu** musi być ustawione na wartość **Domyślne**. Aby uzyskać więcej informacji dotyczące sposobu konfigurowania urzędów skarbowych, zobacz [Konfigurowanie urzędów skarbowych](../general-ledger/tasks/set-up-sales-tax-authorities.md).
- Jeśli księgowane są transakcje podatkowe, które muszą zostać uwzględnione w raporcie JPK_V7M, należy ustawić pole **Data ewidencji VAT**.
- Na stronie **Kody podatku** (**Podatek** > **Podatek pośredni** > **Podatek** > **Kody podatku**) dla kodów podatku używanych w transakcjach podatkowych, które muszą zostać uwzględnione w raporcie JPK_V7M pole **Typ podatku** musi być ustawione na wartość **Standardowy VAT** lub **Obniżony VAT**.
- Na stronie **Kody podatku** dla kodów podatków używanych w transakcjach podatkowych, które muszą być uwzględnione w raporcie JPK_V7M, kody raportowania podatku używane w formacie raportu elektronicznego (ER) muszą być odpowiednio zdefiniowane.

## <a name="prepare-for-jpk_v7m-reporting"></a>Przygotowanie do raportowania JPK_V7M

Rozwiązanie do obsługi raportowania JPK_V7M jest oparte na funkcji [obsługi wiadomości elektronicznych](../general-ledger/electronic-messaging.md). Ta funkcja zapewnia elastyczne podejście do konfigurowania i obsługiwania procesów raportowania.

Poniższe zadania przygotowują Dynamics 365 Finance do raportowania JPK_V7M:

- Importowanie i konfigurowanie konfiguracji ER.
- Konfigurowanie parametrów specyficznych dla aplikacji.
- Importowanie pakietu jednostek danych zawierającego wstępnie zdefiniowaną konfigurację wiadomości elektronicznych.
- Konfigurowanie parametrów księgi głównej.
- Zapisywanie parametrów klasy wykonywalnej dla wiadomości elektronicznych.
- Konfigurowanie ról zabezpieczeń na potrzeby przetwarzania wiadomości elektronicznych.
- Konfigurowanie kodu urzędu na potrzeby przetwarzania wiadomości elektronicznych.

### <a name="import-and-set-up-er-configurations"></a>Importowanie i konfigurowanie konfiguracji ER

Aby przygotować moduł Finance na potrzeby raportowania JPK_V7M, należy zaimportować następujące wersje lub nowsze wersje konfiguracji ER.

| **Nazwa konfiguracji ER**         | **Typ**           | **Opis**                                                                                                 |
|-----------------------------------|--------------------|-----------------------------------------------------------------------------------------------------------------|
| Standardowy plik audytu (SAF-T)       | Model              | Wspólny model ER dla jednolitych plików kontrolnych.                                                                   |
| Mapowanie modelu jednolitego pliku kontrolnego | Mapowanie modelu      | Mapowanie modelu definiujące źródła danych dla raportów polskiego jednolitego pliku kontrolnego (JPK).                       |
| Format XML JPK-V7M (PL)           | Format (eksportowanie) | Format XML dostarczający plik, którego okresowego przesyłania wymaga polskie Ministerstwo Finansów. |
| Format Excel JPK-V7M (PL)         | Format (eksportowanie) | Format programu Excel służący do podglądu informacji, które będą raportowane w formacie XML.                                   |

Importowanie ostatniej wersji tych konfiguracji. Opis wersji zazwyczaj zawiera numer artykułu z bazy wiedzy Microsoft Knowledge Base (KB), który wyjaśnia zmiany wprowadzone w wersji konfiguracji systemu. Narzędzie wyszukiwanie problemów w [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/v2) umożliwia znalezienie artykułu z bazy wiedzy na podstawie numeru.

> [!NOTE]
> Po zaimportowaniu wszystkich konfiguracji ER z poprzedniej tabeli należy zmienić ustawienie opcji **Ustawienie domyślne mapowanie modelu** na **Tak** w przypadku konfiguracji **Mapowanie jednolitych plików kontrolnych** na stronie **Konfiguracje**.
>
> ![Konfiguracja mapowania modelu jednolitego pliku kontrolnego](media/default-mm.jpg)

Aby uzyskać więcej informacji na temat pobierania konfiguracji modułu ER z globalnego repozytorium Microsoft, zapoznaj się z tematem [Pobieranie konfiguracji ER z repozytorium globalnego](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters"></a>Konfigurowanie parametrów specyficznych dla aplikacji

W zależności od danych transakcji podatkowych wartości niektórych elementów raportu JPK_V7M mogą być definiowane na potrzeby raportowania. Aby można było zdefiniować wartości tych elementów, musi być wystarczająco dużo danych transakcyjnych. Dlatego należy skonfigurować odpowiednią liczbę kodów podatków, grup podatków i grup podatków dla towaru, aby rozróżnić transakcje podatkowe dla wszystkich parametrów (elementów) wprowadzonych w raporcie JPK_V7M. Format JPK_V7M zawiera parametry specyficzne dla aplikacji, które mogą być używane do definiowania wartości tych elementów w raporcie.

Format zawiera następujące pola wyszukiwania konfiguracji:

| **Imię i nazwisko**                      | **Opis**                                                                                                                                                                                                                                                                                         | **Wpływ**                                                                                                                                                                                       |
|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ImportSelector                | Oznaczenie, które jest związane z podatkiem naliczonym od przywozu towarów, w tym towarów opodatkowanych zgodnie z artykułem 33a ustawy o VAT                                                                                                                                                            | To pole wyszukiwania służy do definiowania wartości markera **IMP** dla dokumentów zakupu.                                                                                                      |
| ProceduralMarkingsSelector    | Oznaczenia związane z procedurami                                                                                                                                                                                                                                                         | To pole wyszukiwania służy do definiowania wartości następujących markerów dokumentów sprzedaży: **SW**, **EE**, **TP**, **TT-WNT**, **TT_D**, **I_42**, **I_63**, **B_SPV**, and **B_SPV_DOSTAWA**. |
| ServiceDeliverySelector       | Wskaźnik związany z dostawą i świadczeniem usług                                                                                                                                                                                                                                  | To pole wyszukiwania służy do definiowania wartości wszystkich markerów **GTU_\**_ (od _* GTU_1** do **GTU_13**) dla dokumentów sprzedaży.                                                                |
| DeclarationMarkersSelector    | Markery z części deklaracji dla transakcji podatkowych                                                                                                                                                                                                                                                  | To pole wyszukiwania służy do definiowania markerów **P_65** i **P_67** części deklaracji, na podstawie informacji zawartych w dokumencie.                                                           |
| ZakupVAT_MarzaSelector        | Kwota zakupu towarów i usług od innych podatników na bezpośrednią korzyść turystów oraz ilość towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą, które są opodatkowane na podstawie marży, zgodnie z artykułem 120 ustawy o VAT | To pole wyszukiwania służy do definiowania markera **ZakupVAT_Marza** dla dokumentów zakupu.                                                                                                        |
| SalesDocumentTypesSelector    | Oznaczenie typu dokumentu sprzedaży                                                                                                                                                                                                                                                          | To pole wyszukiwania służy do definiowania typów dokumentu sprzedaży **FP**, **RO** i **WEW**.                                                                                                        |
| SprzedazVAT_MarzaSelector     | Wartość sprzedaży brutto dostaw towarów i usług, które są opodatkowane na podstawie marży, zgodnie z artykułami 119 i 120 ustawy o podatku VAT                                                                                                                                                     | To pole wyszukiwania służy do definiowania markera **SprzedazVAT_Marza** dla dokumentów sprzedaży.                                                                                                        |
| PurchaseDocumentTypesSelector | Oznaczenie typu dokumentu zakupu                                                                                                                                                                                                                                                      | To pole wyszukiwania służy do definiowania typów dokumentu zakupu **MK**, **VAT_RR** i **WEW**.                                                                                                 |

1. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
2. Na stronie **Konfiguracje** rozwiń węzeł **Jednolity plik kontrolny (SAF-T)** i wybierz opcję **Format XML JPK-V7M (PL)**.
3. W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.

    ![Grupa parametrów specyficznych dla aplikacji](media/setup-app-spec-params.jpg)

4. Na stronie **Parametry specyficzne dla aplikacji** wybierz najnowszą wersję formatu, dla którego chcesz zdefiniować warunki.
5. Na skróconej karcie **Wyszukiwania** wybierz poszczególne wyszukiwania i zdefiniuj odpowiednie warunki dla nich.
6. Na skróconej karcie **Warunki** określ, które kody podatków lub inne dostępne kryteria muszą odpowiadać określonemu wynikowi wyszukiwania. Jeśli warunki są zdefiniowane w jednym wierszu, system zastosuje je do źródłowej transakcji podatkowej za pomocą operatora **AND**. Jeśli warunki muszą być zastosowane za pomocą operatora **OR**, należy je zdefiniować w oddzielnych wierszach. W momencie, gdy transakcja podatkowa z okresu raportu spełnia warunek z listy, dla powiązanego dokumentu zostanie zgłoszony powiązany marker z wyniku wyszukiwania. Aby uzyskać więcej informacji o ustawieniach pól wyszukiwania, zapoznaj się z podsekcjami znajdującymi się poniżej.
7. W polu **Stan** wybierz opcję **Zakończone**, a następnie zapisz konfigurację.

    ![Pole stanu](media/complete-app-spec-params.jpg)

#### <a name="import-transactions-importtransaction"></a>Transakcje importowe (ImportTransaction)


| **Imię i nazwisko**          | **Etykieta (EN)** | **Etykieta (PL)** | **Opis (EN)**                                                                                                                         | **Opis (PL)**                                                                                                            |
|-------------------|----------------|----------------|----------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| ImportTransaction | Import         | Import         | Oznaczenie, które jest związane z podatkiem naliczonym od przywozu towarów, w tym towarów opodatkowanych zgodnie z artykułem 33a ustawy o VAT | Oznaczenie dotyczące podatku naliczonego z tytułu importu towarów, w tym importu towarów rozliczanego zgodnie z art. 33a ustawy |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kody podatków
- Grupa podatków
- Identyfikator konta dostawcy
- Grupa dostawców

Zdefiniuj warunki na podstawie głównych źródeł danych bieżącej firmy, aby określić, który dokument zakupu musi zostać zgłoszony z wartością **1** w elemencie **\<IMP\>** pod tagiem **\<ZakupWiersz\>**.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **ImportTransaction**.

| **Imię i nazwisko** | **Etykieta (EN)** | &nbsp;  | **Etykieta (PL)** | **Opis (EN)**                                                                                                                         | **Opis (PL)**                                                                                                            |
|----------|----------------|---|----------------|----------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Import   | Import         |   | Import         | Oznaczenie, które jest związane z podatkiem naliczonym od przywozu towarów, w tym towarów opodatkowanych zgodnie z artykułem 33a ustawy o VAT | Oznaczenie dotyczące podatku naliczonego z tytułu importu towarów, w tym importu towarów rozliczanego zgodnie z art. 33a ustawy |
| Inne     | Inna          |   |                |                                                                                                                                              |                                                                                                                                 |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** dla wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

#### <a name="procedural-markings-proceduralmarkingsselector"></a>Oznaczenia dotyczące procedur (ProceduralMarkingsSelector)

| **Imię i nazwisko**                   | **Etykieta (EN)**      | **Etykieta (PL)**                | **Opis (EN)**                            | **Opis (PL)**          |
|----------------------------|---------------------|-------------------------------|-------------------------------------------------|-------------------------------|
| ProceduralMarkingsSelector | Oznaczenia dotyczące procedur | Oznaczenia dotyczące procedur | Oznaczenia związane z procedurami | Oznaczenia dotyczące procedur |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do konfigurowania warunków:

- Kody podatków
- Grupa podatków
- Identyfikator konta odbiorcy
- Grupa odbiorców

To pole wyszukiwania definiuje warunki oparte na głównych źródłach danych bieżącej firmy. Warunki te dają w wyniku marker **1** dla odpowiadającego mu elementu z listy oznaczeń, które są związane z procedurami pod tagiem **\<SprzedazWiersz\>**. Można zaznaczyć więcej niż jedno oznaczenie dla tego samego rekordu należnego podatku VAT. Dlatego, jeśli firma musi zgłosić odmienne oznaczenia, muszą być zdefiniowane odrębne warunki.

W poniższej tabeli przedstawiono wyniki wyszukiwania (oznaczenia) dla **ProceduralMarkingsSelector**.

| **Imię i nazwisko**       | **Etykieta (EN)**                                                                                            | **Etykieta (PL)**                                                         | **Opis (EN)**                                                                                                                                                                                         | **Opis (PL)**                                                                                                                                                                               |
|----------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SW             | Sprzedaż wysyłkowa                                                                                           | Sprzedaży wysyłkowej                                                   | Dostawa w ramach sprzedaży wysyłkowej z terytorium kraju, o której mowa w art. 23 ustawy o VAT                                                                                         | Dostawa w ramach sprzedaży wysyłkowej z terytorium kraju, o której mowa w art. 23 ustawy                                                                                                           |
| EE             | Telekomunikacja                                                                                        | Usługi telekomunikacyjne                                              | Świadczenie usług telekomunikacyjnych, nadawczych i elektronicznych, o których mowa w art. 28k ustawy o VAT                                                                                | Świadczenie usług telekomunikacyjnych, nadawczych i elektronicznych, o których mowa w art. 28k ustawy                                                                                              |
| TP             | Istniejące powiązania między nabywcą a dokonującym dostawy                                                                  | Istniejące powiązania między nabywcą a dokonującym                     | Istniejące powiązania między kupującym a dostawcą towarów lub usługodawcą w rozumieniu art. 32, sekcja 2, pkt 1 ustawy o podatku VAT                                                      | Istniejące powiązania między nabywcą a dokonującym dostawy towarów lub usługodawcą, o których mowa w art. 32 ust. 2 pkt 1 ustawy                                                                   |
| TT_WNT         | Wewnątrzwspólnotowe nabycie w ramach transakcji trójstronnej                                          | Wewnątrzwspólnotowe nabycie w ramach transakcji trójstronnej           | Wewnątrzwspólnotowe nabycie towarów dokonane przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy o VAT | Wewnątrzwspólnotowe nabycie towarów dokonane przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy   |
| TT_D           | Dostawa towarów poza terytorium Polski w ramach transakcji trójstronnej                                     | Dostawa towarów poza terytorium kraju w ramach transakcji trójstronnej | Dostawa towarów poza terytorium kraju dokonana przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy o VAT   | Dostawa towarów poza terytorium kraju dokonana przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy |
| I_42           | Procedura celna 42 (import)                                                                             | Procedura celna 42 (import)                                           | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 42 (import)                                                                                                              | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 42 (import)                                                                                     |
| I_63           | Procedura celna 63 (import)                                                                             | Procedura celna 63 (import)                                            | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 63 (import)                                                                                                              | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 63 (import)                                                                                     |
| B_SPV          | Transfer z artykułu 8A, ustęp 1 ustawy o VAT                                                        | Transfer z art. 8a ust. 1 ustawy                                       | Transfer bonu jednego przeznaczenia dokonany przez podatnika działającego własnym imieniu, opodatkowany zgodnie z art. 8a ustęp 1 ustawy o VAT                           | Transfer bonu jednego przeznaczenia dokonany przez podatnika działającego we własnym imieniu, opodatkowany zgodnie z art. 8a ust. 1 ustawy                                                         |
| B_SPV_DOSTAWA  | Dostawa towarów oraz świadczenie usług, których dotyczy Bon jednego przeznaczenia (artykuł 8a, ustęp 4 ustawy o VAT) | Dostawa towarów oraz świadczenie usług (art. 8a ust. 4 ustawy)         | Dostawa towarów oraz świadczenie usług, których dotyczy bon jednego przeznaczenia na rzecz podatnika, który wyemitował bon zgodnie z art. 8a, ustęp 4 ustawy o VAT          | Dostawa towarów oraz świadczenie usług, których dotyczy bon jednego przeznaczenia na rzecz podatnika, który wyemitował bon zgodnie z art. 8a ust. 4 ustawy                                         |
| B_MPV_PROWIZJA | Usługi pośrednictwa dotyczące bonów różnego przeznaczenia                                                             | Usługi pośrednictwa dotyczące transferu bonu różnego przeznaczenia              | Świadczenie usług pośrednictwa oraz innych usług dotyczących transferu bonu różnego przeznaczenia, opodatkowane zgodnie z art. 8b, ustęp 2 ustawy o VAT                            | Świadczenie usług pośrednictwa oraz innych usług dotyczących transferu bonu różnego przeznaczenia, opodatkowane zgodnie z art. 8b ust. 2 ustawy                                                    |
| Inne           | Inna                                                                                                     |                                                                        |                                                                                                                                                                                                              |                                                                                                                                                                                                    |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** dla wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

#### <a name="goods-and-services-supplying-types-servicedeliveryselector"></a>Typy dostawy towarów i usług (ServiceDeliverySelector)


| **Imię i nazwisko**                | **Etykieta (EN)**                     | **Etykieta (PL)**              | **Opis (EN)**                                                   | **Opis (PL)**                             |
|-------------------------|------------------------------------|-----------------------------|------------------------------------------------------------------------|--------------------------------------------------|
| ServiceDeliverySelector | Dostawy i świadczenia usług | Dostawy I świadczenia usług | Wskaźnik związany z dostawą i świadczeniem usług | Oznaczenie dotyczące dostawy i świadczenia usług |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Identyfikator konta odbiorcy
- Grupa odbiorców

To pole wyszukiwania definiuje warunki oparte na głównych źródłach danych bieżącej firmy. Warunki te dają w wyniku marker **1** dla odpowiadającego mu elementu z listy oznaczeń, które są związane z dostawami i świadczeniem usług pod tagiem **\<SprzedazWiersz\>**. Można zaznaczyć więcej niż jedno oznaczenie dla tego samego rekordu należnego podatku VAT. Dlatego, jeśli firma musi zgłosić odmienne oznaczenia, muszą być dostępne odrębne warunki w danych głównych firmy.

W poniższej tabeli przedstawiono wyniki wyszukiwania (oznaczenia) dla **ServiceDeliverySelector**.

| **Imię i nazwisko** | **Etykieta (EN)**                                      | **Etykieta (PL)**                                      | **Opis (EN)**                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | **Opis (PL)**                                                                                                                                                                                                                                                                                                                                                                                                                        |
|----------|-----------------------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GTU_01   | Dostawa napojów alkoholowych                       | Dostawa napojów alkoholowych                        | Dostawa napojów alkoholowych - alkoholu etylowego, piwa, wina, napojów fermentowanych i wyrobów pośrednich, w rozumieniu przepisów o podatku akcyzowym                                                                                                                                                                                                                                                                                                                          | Dostawa napojów alkoholowych - alkoholu etylowego, piwa, wina, napojów fermentowanych i wyrobów pośrednich, w rozumieniu przepisów o podatku akcyzowym                                                                                                                                                                                                                                                                                      |
| GTU_02   | Dostawa towarów, o których mowa w art. 103, poz. 5aa | Dostawa towarów, o których mowa w art. 103 ust. 5aa | Dostawa towarów, o których mowa w art. 103, poz. 5aa ustawy o VAT                                                                                                                                                                                                                                                                                                                                                                                                           | Dostawa towarów, o których mowa w art. 103 ust. 5aa ustawy                                                                                                                                                                                                                                                                                                                                                                                  |
| GTU_03   | Dostawa oleju opałowego                               | Dostawa oleju opałowego                             | Dostawa oleju opałowego w rozumieniu przepisów o podatku akcyzowym oraz olejów smarowych, pozostałych olejów o kodach CN od 2710 19 71 do 2710 19 99, z wyłączeniem wyrobów o kodzie CN 2710 19 85 (oleje białe, parafina ciekła) oraz smarów plastycznych zaliczanych do kodu CN 2710 19 99, olejów smarowych o kodzie CN 2710 20 90, preparatów smarowych objętych pozycją CN 3403, z wyłączeniem smarów plastycznych objętych tą pozycją | Dostawa oleju opałowego w rozumieniu przepisów o podatku akcyzowym oraz olejów smarowych, pozostałych olejów o kodach CN od 2710 19 71 do 2710 19 99, z wyłączeniem wyrobów o kodzie CN 2710 19 85 (oleje białe, parafina ciekła) oraz smarów plastycznych zaliczanych do kodu CN 2710 19 99, olejów smarowych o kodzie CN 2710 20 90, preparatów smarowych objętych pozycją CN 3403, z wyłączeniem smarów plastycznych objętych tą pozycją |
| GTU_04   | Dostawa wyrobów tytoniowych                          | Dostawa wyrobów tytoniowych                         | Dostawa wyrobów tytoniowych, suszu tytoniowego, płynu do papierosów elektronicznych i wyrobów nowatorskich, w rozumieniu przepisów o podatku akcyzowym                                                                                                                                                                                                                                                                                                                       | Dostawa wyrobów tytoniowych, suszu tytoniowego, płynu do papierosów elektronicznych i wyrobów nowatorskich, w rozumieniu przepisów o podatku akcyzowym                                                                                                                                                                                                                                                                                      |
| GTU_05   | Dostawa odpadów                                   | Dostawa odpadów                                     | Dostawa odpadów - wyłącznie określonych w poz. od 79 do 91 załącznika 15 do ustawy o VAT                                                                                                                                                                                                                                                                                                                                                                                     | Dostawa odpadów - wyłącznie określonych w poz. 79-91 załącznika nr 15 do ustawy                                                                                                                                                                                                                                                                                                                                                             |
| GTU_06   | Dostawa urządzeń elektronicznych                        | Dostawa urządzeń elektronicznych                    | Dostawa urządzeń elektronicznych oraz części i materiałów do nich, wyłącznie określonych w poz. 7-9, 59-63, 65, 66, 69 i 94-96 załącznika nr 15 do ustawy o VAT                                                                                                                                                                                                                                                                                                   | Dostawa urządzeń elektronicznych oraz części i materiałów do nich, wyłącznie określonych w poz. 7-9, 59-63, 65, 66, 69 i 94-96 załącznika nr 15 do ustawy                                                                                                                                                                                                                                                                                   |
| GTU_07   | Dostawa pojazdów                                  | Dostawa pojazdów                                    | Dostawa pojazdów oraz części samochodowych o kodach wyłącznie CN 8701 - 8708 oraz CN 8708 10                                                                                                                                                                                                                                                                                                                                                                                                | Dostawa pojazdów oraz części samochodowych o kodach wyłącznie CN 8701 - 8708 oraz CN 8708 10                                                                                                                                                                                                                                                                                                                                                |
| GTU_08   | Dostawa metali szlachetnych oraz nieszlachetnych                | Dostawa metali szlachetnych oraz nieszlachetnych    | Dostawa metali szlachetnych oraz nieszlachetnych - wyłącznie określonych w poz. 1-3 załącznika nr 12 do ustawy o VAT oraz w poz. 12-25, 33-40, 45, 46, 56 i 78 załącznika nr 15 do ustawy o VAT                                                                                                                                                                                                                                                                 | Dostawa metali szlachetnych oraz nieszlachetnych - wyłącznie określonych w poz. 1-3 załącznika nr 12 do ustawy oraz w poz. 12-25, 33-40, 45, 46, 56 i 78 załącznika nr 15 do ustawy                                                                                                                                                                                                                                                         |
| GTU_09   | Dostawa leków oraz wyrobów medycznych             | Dostawa leków oraz wyrobów medycznych               | Dostawa leków oraz wyrobów medycznych - produktów leczniczych, środków spożywczych specjalnego przeznaczenia żywieniowego oraz wyrobów medycznych, objętych obowiązkiem zgłoszenia, o którym mowa w art. 37av ust. 1 ustawy z dnia 6 września 2001 r. - Prawo farmaceutyczne (Dz. U. z 2019 r. poz. 499, z późniejszymi zmianami)                                                                                                                                          | Dostawa leków oraz wyrobów medycznych - produktów leczniczych, środków spożywczych specjalnego przeznaczenia żywieniowego oraz wyrobów medycznych, objętych obowiązkiem zgłoszenia, o którym mowa w art. 37av ust. 1 ustawy z dnia 6 września 2001 r. - Prawo farmaceutyczne (Dz. U. z 2019 r. poz. 499, z późn. zm.)                                                                                                                       |
| GTU_10   | Dostawa budynków                                 | Dostawa budynków                                    | Dostawa budynków, budowli i gruntów                                                                                                                                                                                                                                                                                                                                                                                                                                                | Dostawa budynków, budowli i gruntów                                                                                                                                                                                                                                                                                                                                                                                                         |
| GTU_11   | Świadczenie usług — gazy cieplarniane                | Świadczenie usług — gazy cieplarniane          | Świadczenie usług w zakresie przenoszenia uprawnień do emisji gazów cieplarnianych, o których mowa w ustawie z dnia 12 czerwca 2015 r. o systemie handlu uprawnieniami do emisji gazów cieplarnianych (Dz. U. z 2018 r. poz. 1201 i 2538 oraz z 2019 r. poz. 730, 1501 i 1532)                                                                                                                                                                           | Świadczenie usług w zakresie przenoszenia uprawnień do emisji gazów cieplarnianych, o których mowa w ustawie z dnia 12 czerwca 2015 r. o systemie handlu uprawnieniami do emisji gazów cieplarnianych (Dz. U. z 2018 r. poz. 1201 i 2538 oraz z 2019 r. poz. 730, 1501 i 1532)                                                                                                                                                              |
| GTU_12   | Świadczenie usług o charakterze niematerialnym                    | Świadczenie usług o charakterze niematerialnym      | Świadczenie usług o charakterze niematerialnym - wyłącznie: doradczych, księgowych, prawnych, zarządczych, szkoleniowych, marketingowych, firm centralnych (head offices), reklamowych, badania rynku i opinii publicznej, w zakresie badań naukowych i prac rozwojowych                                                                                                                                                                                                                                                    | Świadczenie usług o charakterze niematerialnym - wyłącznie: doradczych, księgowych, prawnych, zarządczych, szkoleniowych, marketingowych, firm centralnych (head offices), reklamowych, badania rynku i opinii publicznej, w zakresie badań naukowych i prac rozwojowych                                                                                                                                                                    |
| GTU_13   | Świadczenie usług transportowych i gospodarki magazynowej           | Świadczenie usług transportowych i gospodarki magazynowej       | Świadczenie usług transportowych i gospodarki magazynowej - Sekcja H PKWiU 2015 symbol ex 49.4, ex 52.1                                                                                                                                                                                                                                                                                                                                                                     | Świadczenie usług transportowych i gospodarki magazynowej - Sekcja H PKWiU 2015 symbol ex 49.4, ex 52.1                                                                                                                                                                                                                                                                                                                                     |
| Inne     | Inna                                               |                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                             |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** dla wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

#### <a name="declaration-markers-declarationmarkersselector"></a>Markery deklaracji (DeclarationMarkersSelector)

| **Imię i nazwisko**                   | **Etykieta (EN)**      | **Etykieta (PL)**     | **Opis (EN)**                                   | **Opis (PL)**                                     |
|----------------------------|---------------------|--------------------|--------------------------------------------------------|----------------------------------------------------------|
| DeclarationMarkersSelector | Markery deklaracji | Markery deklaracji | Markery z części deklaracji dla transakcji podatkowych | Znaczniki z części deklaracji dla transakcji podatkowych |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Grupa podatków
- Identyfikator konta odbiorcy
- Grupa odbiorców
- Identyfikator konta dostawcy
- Grupa dostawców

To pole wyszukiwania definiuje warunki oparte na głównych źródłach danych bieżącej firmy. Warunki te wygenerują znak **1** dla elementów **P_65** i **P_67** części **\<Deklaracja\>** raportu, jeśli będzie je spełniał co najmniej jeden dokument w okresie raportu.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **DeclarationMarkersSelector**.

| **Imię i nazwisko** | **Etykieta (EN)**                               | **Etykieta (PL)**                             | **Opis (EN)**                                                                                                                                               | **Opis (PL)**                                                                     |
|----------|----------------------------------------------|--------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| P_65     | Czynności, o których mowa w art. 122 | Czynności o których mowa w art. 122 ustawy | Podatnik wykonywał w okresie rozliczeniowym czynności, o których mowa w art. 122 ustawy o VAT. Zwolnienie z podatku dostawy, importu i zakupu złota inwestycyjnego | Podatnik wykonywał w okresie rozliczeniowym czynności, o których mowa w art. 122 ustawy  |
| P_65     | Obniżenie kwoty zobowiązania podatkowego                      | Obniżenie kwoty zobowiązania podatkowego   | Podatnik korzysta z obniżenia zobowiązania podatkowego, o którym mowa w art. 108d ustawy o VAT                                                   | Podatnik korzysta z obniżenia zobowiązania podatkowego, o którym mowa w art. 108d ustawy |
| Inne     | Inna                                        |                                            |                                                                                                                                                                    |                                                                                          |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

#### <a name="input-vat--margin-zakupvat_marzaselector"></a>Naliczony podatek VAT — marża (ZakupVAT_MarzaSelector)

| **Imię i nazwisko**               | **Etykieta (EN)**      | **Etykieta (PL)**      | **Opis (EN)**                                                                                                                                                                                                                                                                                    | **Opis (PL)**                                                                                                                                                                                                                                                     |
|------------------------|---------------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ZakupVAT_MarzaSelector | Markery deklaracji | Podatek VAT — marża | Kwota zakupu towarów i usług od innych podatników na bezpośrednią korzyść turystów oraz ilość towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą, które są opodatkowane na podstawie marży, zgodnie z artykułem 120 ustawy o VAT | Kwota nabycia towarów i usług nabytych od innych podatników dla bezpośredniej korzyści turysty, a także nabycia towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą opodatkowaną na zasadzie marży zgodnie z art. 120 ustawy |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji

To pole wyszukiwania umożliwia zdefiniowanie różnych warunków poboru kwot, które muszą być zgłaszane w elemencie **ZakupWiersz/ZakupVAT_Marza** w raporcie. System zbiera kwoty brutto transakcji podatkowych spełniających określone kryteria. Jeśli warunki są zdefiniowane w jednym wierszu konfiguracji, system zastosuje je do źródłowej transakcji podatkowej za pomocą operatora **AND**. Jeśli warunki muszą być zastosowane za pomocą operatora **OR**, należy je zdefiniować w oddzielnych wierszach. W momencie, gdy transakcja podatkowa z okresu raportu spełnia warunek z listy, powiązana kwota brutto zostanie zebrana na potrzeby raportowania w elemencie **ZakupWiersz/ZakupVAT_Marza** raportu w odniesieniu do dokumentu.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **ZakupVAT_MarzaSelector**.

| **Imię i nazwisko**       | **Etykieta (EN)**     | **Etykieta (PL)**      | **Opis (EN)**                                                                                                                                                                                                                                                                                    | **Opis (PL)**                                                                                                                                                                                                                                                     |
|----------------|--------------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ZakupVAT_Marza | Naliczony podatek VAT — marża | Podatek VAT — marża | Kwota zakupu towarów i usług od innych podatników na bezpośrednią korzyść turystów oraz ilość towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą, które są opodatkowane na podstawie marży, zgodnie z artykułem 120 ustawy o VAT | Kwota nabycia towarów i usług nabytych od innych podatników dla bezpośredniej korzyści turysty, a także nabycia towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą opodatkowaną na zasadzie marży zgodnie z art. 120 ustawy |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

#### <a name="document-types-for-sales-salesdocumenttypesselector"></a>Typy dokumentów dla sprzedaży (SalesDocumentTypesSelector)

| **Imię i nazwisko**                   | **Etykieta (EN)** | **Etykieta (PL)** | **Opis (EN)**                            | **Opis (PL)**        |
|----------------------------|----------------|----------------|-------------------------------------------------|-----------------------------|
| SalesDocumentTypesSelector | Typ dokumentu   | Typ dokumentu  | Oznaczenie typu dokumentu sprzedaży | Oznaczenie dowodu sprzedaży |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Grupa podatków
- Identyfikator konta odbiorcy
- Grupa odbiorców

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **SalesDocumentTypesSelector**.

| **Imię i nazwisko** | **Etykieta (EN)**                                                   | **Etykieta (PL)**                                   | **Opis (EN)**                                                                              | **Opis (PL)**                                                   |
|----------|------------------------------------------------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
| FP       | Faktura, o której mowa w art. 109, ust. 3d | Faktura, o której mowa w art. 109 ust. 3d ustawy | Faktura, o której mowa w art. 109, ust. 3d ustawy o VAT | Faktura, o której mowa w art. 109 ust. 3d ustawy                       |
| RO       | Dokument zbiorczy wewnętrzny                                        | Dokument zbiorczy wewnętrzny                     | Dokument zbiorczy wewnętrzny zawierający sprzedaż z kas rejestrujących                              | Dokument zbiorczy wewnętrzny zawierający sprzedaż z kas rejestrujących |
| WEW      | Dokument wewnętrzny                                                | Dokument wewnętrzny                              | Dokument wewnętrzny                                                                                 | Dokument wewnętrzny                                                    |
| Inne     | Inna                                                            |                                                  |                                                                                                   |                                                                        |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

Aby uzyskać więcej informacji dotyczących sposobu raportowania typów dokumentów **RO** i **FP** dla operacji handlu detalicznego, zapoznaj się z sekcją „Raportowanie typów dokumentów RO i FP dla operacji handlu detalicznego” w dalszej części tego tematu.

#### <a name="output-vat--margin-sprzedazvat_marzaselector"></a>Należny podatek VAT — marża (SprzedazVAT_MarzaSelector)

| **Imię i nazwisko**                  | **Etykieta (EN)**      | **Etykieta (PL)**      | **Opis (EN)**                                                                                                                                | **Opis (PL)**                                                                                                               |
|---------------------------|---------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| SprzedazVAT_MarzaSelector | Należny podatek VAT — marża | VAT należny — marża | Wartość sprzedaży brutto dostaw towarów i usług, które są opodatkowane na podstawie marży, zgodnie z artykułami 119 i 120 ustawy o podatku VAT | Wartość sprzedaży brutto dostawy towarów i świadczenia usług opodatkowanych na zasadach marży zgodnie z art. 119 i art. 120 ustawy |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji

To pole wyszukiwania umożliwia definiowanie różnych warunków w celu raportowania markera **MR_T** lub **MR_UZ** dla dokumentów sprzedaży w elemencie **SprzedazWiersz** raportu.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **SprzedazVAT_MarzaSelector**.

| **Imię i nazwisko** | **Etykieta (EN)**                                    | **Etykieta (PL)**                                 | **Opis (EN)**                                                                                                                                           | **Opis (PL)**                                                                                                                      |
|----------|---------------------------------------------------|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| MR_T     | Usług turystyki opodatkowane na zasadach marży | Usług turystyki opodatkowane na zasadach marży | Świadczenie usług turystyki opodatkowane na zasadach marży zgodnie z art. 119 ustawy o VAT                                              | Świadczenie usług turystyki opodatkowane na zasadach marży zgodnie z art. 119 ustawy                                                      |
| MR_UZ    | Dostawa towarów używanych, dzieł sztuki i antyków              | Dostawa towarów używanych, dzieł sztuki i antyków       | Dostawa towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków, opodatkowana na zasadach marży zgodnie z art. 120 ustawy o VAT | Dostawa towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków, opodatkowana na zasadach marży zgodnie z art. 120 ustawy |
| Inne     | Inna                                             |                                                |                                                                                                                                                                |                                                                                                                                           |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

#### <a name="document-types-for-purchases-purchasedocumenttypesselector"></a>Typy dokumentów dla zakupów (PurchaseDocumentTypesSelector)

| **Imię i nazwisko**                      | **Etykieta (EN)**        | **Etykieta (PL)**  | **Opis (EN)**                               | **Opis (PL)**     |
|-------------------------------|-----------------------|-----------------|----------------------------------------------------|--------------------------|
| PurchaseDocumentTypesSelector | Typ faktury zakupu | Dokument zakupu | Oznaczenie typu dokumentu zakupu | Oznaczenie dowodu zakupu |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Grupa podatków
- Identyfikator konta dostawcy
- Grupa dostawców

To pole wyszukiwania wyznacza kombinację kodu podatku (**Kod podatku**), identyfikatora konta dostawcy ID (**Identyfikator konta**) i grupy dostawców (**PartyGroup**) z bazy danych bieżącej firmy, z której będzie generowany typ dokumentu pod tagiem **\<ZakupWiersz\>**. Istnieje kilka kombinacji, które mogą być zdefiniowane.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **PurchaseDocumentTypesSelector**.

| **Imię i nazwisko** | **Etykieta (EN)**                             | **Etykieta (PL)**          | **Opis (EN)**                                                                                                                                                          | **Opis (PL)**                                                                                                                  |
|----------|--------------------------------------------|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| MK       | Faktura, o której mowa w art. 21  | Faktura art. 21         | Faktura wystawiona przez podatnika będącego dostawcą lub usługodawcą, który wybrał metodę kasową rozliczeń określoną w art. 21 ustawy o VAT | Faktura wystawiona przez podatnika będącego dostawcą lub usługodawcą, który wybrał metodę kasową rozliczeń określoną w art. 21 ustawy |
| VAT_RR   | Faktura, o której mowa w art. 116 | Faktura VAT RR, art. 116 | Faktura VAT RR, o której mowa w art. 116 ustawy o VAT                                                                                                             | Faktura VAT RR, o której mowa w art. 116 ustawy                                                                                       |
| WEW      | Dokument wewnętrzny                          | Dokument wewnętrzny     | Dokument wewnętrzny                                                                                                                                                             | Dokument wewnętrzny                                                                                                                   |
| Inne     | Inna                                      |                         |                                                                                                                                                                               |                                                                                                                                       |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="import-a-package-of-data-entities-that-includes-a-predefined-electronic-message-setup"></a>Importowanie pakietu jednostek danych zawierającego wstępnie zdefiniowaną konfigurację wiadomości elektronicznych

Proces konfigurowania funkcji obsługi wiadomości elektronicznych do raportowania JPK_V7M ma wiele kroków. Ponieważ nazwy niektórych wstępnie zdefiniowanych jednostek są używane w konfiguracjach ER, ważne jest, aby użyć zbioru wstępnie zdefiniowanych wartości, które są dostarczane w pakiecie jednostek danych dla powiązanych tabel.

1. W [LCS](https://lcs.dynamics.com/v2), w obszarze **Biblioteka udostępnionych elementów** wybierz typ zasobu **Pakiet danych**. Następnie znajdź plik **PL JPK_V7M EM setup**.**zip** na liście plików pakietu danych i pobierz go do komputera.
2. Gdy plik PL JPK_V7M EM setup.zip zostanie pobrany, otwórz moduł Finance, wybierz firmę, z której będzie generowany JPK_VDEK, a następnie przejdź do **Obszary robocze** \> **Zarządzanie danymi**.
3. Przed zaimportowaniem danych konfiguracyjnych z pakietu jednostek danych należy wykonać następujące kroki, aby jednostki danych w aplikacji były odświeżane i synchronizowane.
4. W obszarze roboczym **Zarządzanie danymi** przejdź do **Parametry struktury** \> **Ustawienia jednostki**, a następnie wybierz pozycję **Odśwież listę jednostek**. Poczekaj na potwierdzenie, że odświeżanie zostało zakończone. Aby uzyskać więcej informacji na temat odświeżania listy jednostek, zapoznaj się z tematem [odświeżanie listy jednostek](../../fin-ops-core/dev-itpro/data-entities/data-entities.md#entity-list-refresh).
5. Sprawdź, czy dane źródłowe i dane docelowe są prawidłowo zmapowane. Aby uzyskać więcej informacji, zapoznaj się z sekcją dotyczącą sprawdzania poprawności w [Zadania importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md#validate-that-the-source-data-and-target-data-are-mapped-correctly).
6. Zanim jednostki danych zostaną użyte po raz pierwszy do importowania danych z pakietu, należy zsynchronizować mapowanie danych źródłowych i danych docelowych. Na liście dla pakietu wybierz jednostkę danych, a następnie w okienku akcji wybierz opcję **Modyfikuj mapowanie celu**. Następnie, nad siatką dla pakietu, wybierz opcję **Generuj mapowanie**, aby utworzyć mapowanie od początku.
7. Zapisz mapowanie.
8. Powtórz kroki od 3 do 4 dla każdej jednostki danych w pakiecie.

Aby uzyskać więcej informacji o zarządzaniu danymi, zobacz [Zarządzanie danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Teraz musisz zaimportować dane z pliku PL JPK_V7M EM setup.zip do wybranej firmy.

1. W obszarze roboczym **Zarządzanie danymi** wybierz opcję **Import**, w polu **Format danych źródłowych** wybierz opcję **Pakiet** i utwórz nowy projekt importowania, naciskając przycisk Nowy w okienku akcji.
2. Kliknij przycisk Dodaj plik na skróconej karcie Wybierz jednostki.
3. Wybierz **Przekaż i dodaj**, wybierz plik **PL JPK_V7M EM setup**.**zip** na komputerze i przekaż go.
4. Kliknij przycisk Zamknij, gdy jednostki z pakietu zostaną wyszczególnione na liście w siatce.
5. Kliknij przycisk Importuj w okienku akcji, aby rozpocząć importowanie danych z jednostek danych.

    ![Strona ustawień EM PL JPK_V7M](media/import-data-entities.jpg)

Otrzymasz powiadomienie w obszarze **Komunikaty** lub możesz odświeżyć stronę, aby wyświetlić postęp importowania danych. Po zakończeniu procesu importowania na stronie **Podsumowanie wykonywania** zostaną wyświetlone wyniki.

![Strona podsumowania wykonywania](media/data-entities-imported.jpg)

> [!IMPORTANT]
> Niektóre rekordy z jednostek danych w pakiecie zawierają łącze do konfiguracji ER. Dlatego przed rozpoczęciem importu pakietu jednostek danych należy najpierw zaimportować konfiguracje ER do modułu Finance.

### <a name="set-up-general-ledger-parameters"></a>Konfigurowanie parametrów księgi głównej

Aby pracować z funkcją obsługi wiadomości elektronicznych, należy zdefiniować powiązane sekwencje numerów.

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Parametry księgi głównej**.
2. Na karcie **Sekwencje numerów** skonfiguruj dwie sekwencje numerów:

    - Komunikat
    - Element wiadomości

### <a name="save-the-executable-class-parameters-for-electronic-messaging"></a>Zapisywanie parametrów klasy wykonywalnej dla wiadomości elektronicznych

Podczas przetwarzania JPK_V7M używana jest klasa wykonywalna **EMGenerateJPKVDEKReportController_PL** w celu zainicjowania zbierania danych dla dostawcy danych raportu i dalszego generowania raportu. Przed pierwszym użyciem tej klasy należy zapisać jej parametry.

1. Przejdź do **Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Ustawienia klasy wykonywalnej**.
2. Wybierz klasę wykonywalną **Wygenerowanie JPK_V7M** (która ma wywoływać **EMGenerateJPKVDEKReportController_PL**), a następnie, w okienku akcji, wybierz **Parametry**. W oknie dialogowym **Generuj polski raport JPK_VDEK** naciśnij **OK**.

W oknie dialogowym klasy wykonywalnej grupa parametrów **Oznaczenie sprzedaży właściwe dla sprzedaży detalicznej** jest używana w scenariuszach właściwych dla sprzedaży detalicznej. Aby uzyskać więcej informacji dotyczących sposobu raportowania typów dokumentów **RO** i **FP** dla operacji handlu detalicznego, zapoznaj się z sekcją „Raportowanie typów dokumentów RO i FP dla operacji handlu detalicznego” w dalszej części tego tematu.

### <a name="set-up-security-roles-for-electronic-message-processing"></a>Konfigurowanie ról zabezpieczeń na potrzeby przetwarzania wiadomości elektronicznych

Różne grupy użytkowników mogą wymagać dostępu do przetwarzania JPK_V7M. Można ograniczyć dostęp do przetwarzania na podstawie grup zabezpieczeń zdefiniowanych w systemie.

Aby ograniczyć dostęp do przetwarzania JPK_V7M, należy wykonać następujące kroki.

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Przetwarzanie wiadomości elektronicznych**.
2. Wybierz przetwarzanie **JPK_V7M** i dodaj grupy zabezpieczeń, które muszą na nim pracować, na skróconej karcie **Role zabezpieczeń**. Jeśli dla przetwarzania nie zdefiniowano grupy zabezpieczeń, tylko administrator systemu może go zobaczyć na stronie **Wiadomości elektroniczne**.

### <a name="set-up-an-office-code-for-electronic-message-processing"></a>Konfigurowanie kodu urzędu na potrzeby przetwarzania wiadomości elektronicznych

Aby wprowadzić kod urzędu w dodatkowym polu **KodUrzedu**, należy wykonać poniższe kroki.

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Przetwarzanie wiadomości elektronicznych**.
2. Wybierz Przetwarzanie **JPK-V7M**.
3. Na skróconej karcie **Dodatkowe pole** wybierz dodatkowe pole **KodUrzedu**, a następnie, w polu **Wartość domyślna** określ kod urzędu, który ma być raportowany w elemencie \<**KodUrzedu**\> raportu.

## <a name="jpk-v7m-reporting"></a>Raportowanie JPK-V7M

Proces raportowania JPK-V7M jest wstępnie zdefiniowany przez jednostki danych, które zostały dostarczone w pakiecie PL JPK_V7M EM setup.zip. Na poniższej ilustracji przedstawiono przegląd procesu.

![Przepływ procesu raportowania JPK_V7M](media/vdek-em-processing.jpg)

Pakiet PL JPK_V7M EM setup.zip zawiera ustawienia przetwarzania JPK-V7M, które obsługują proces raportowania JPK-V7M. Ta konfiguracja składa się z następujących kroków:

- **Tworzyć** — utworzenie wiadomości elektronicznej do raportowania JPK-V7M.
- **Wygeneruj plik** — generowanie pliku XML w formacie JPK-V7M.
- **Podgląd w programie Excel** — generowanie raportu JPK-V7M w formacie programu Excel do podglądu.
- **Zmień status** — zmiana stanu wiadomości elektronicznej.

### <a name="initial-assumptions-for-the-jpk-v7m-report"></a>Wstępne założenia dotyczące raportu JPK-V7M

Implementacja raportu JPK-V7M bazuje na tych samych kodach raportowania podatku, które zostały użyte w raporcie JPK_VAT. Aby uzyskać więcej informacji, zobacz temat [Ewidencja zakupów i sprzedaży VAT JPK](emea-pol-standard-audit-file-saf.md#generate-a-saf-vat-sales-and-purchase-register).

W poniższej tabeli przedstawiono kody raportowania podatku używane w raporcie JPK_VAT i ich mapowanie z elementami **K_\** _ raportu JPK-V7M.

| _ *Nazwa elementu** | **Opis elementu**                                                                                                                                                                                                                                                     | **Kody raportowania podatku**                                                                            |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| K_10             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, zwolnionych od podatku                                                                                                                                                                                 | 10302, 10402, 10502, 10602                                                                               |
| K_11             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług poza terytorium Polski                                                                                                                                                                                                       | 10101, 10102, 10104, 10105, 10201, 10204                                                                 |
| K_12             | Wysokość podstawy opodatkowania wynikająca ze świadczenia usług, o których mowa w art. 100 ust. 1 pkt 4 ustawy o VAT                                                                                                                                                              | 10201, 10204                                                                                             |
| K_13             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 0%                                                                                                                                                                                     | 10601, 10604, 10701, 10702, 10704, 10705                                                                 |
| K_14             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów, o której mowa w art. 129 ustawy o VAT                                                                                                                                                                                     | 10701, 10702, 10704, 10705                                                                               |
| K_15             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 5%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT                                                                                                 | 10501, 10504                                                                                             |
| K_16             | Wysokość podatku należnego wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 5%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT                                                                                           | 10503, 10506                                                                                             |
| K_17             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 7% lub 8%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT                                                                                     | 10401, 10404                                                                                             |
| K_18             | Wysokość podatku należnego wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 7% lub 8%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT                                                                              | 10403, 10406                                                                                             |
| K_19             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 22% lub 23%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT                                                                                 | 10301, 10304                                                                                             |
| K_20             | Wysokość podatku należnego wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 22% lub 23%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT                                                                             | 10303, 10306                                                                                             |
| K_21             | Wysokość podstawy opodatkowania wynikająca z wewnątrzwspólnotowej dostawy towarów, o której mowa w art. 13 ust. 1 i 3 ustawy o VAT                                                                                                                                                  | 10807                                                                                                    |
| K_22             | Wysokość podstawy opodatkowania wynikająca z eksportu towarów                                                                                                                                                                                                                                   | 10901, 10905                                                                                             |
| K_23             | Wysokość podstawy opodatkowania wynikająca z wewnątrzwspólnotowego nabycia towarów                                                                                                                                                                                                              | 10810, 10811 (zmiana zwrotna)                                                                            |
| K_24             | Wysokość podatku należnego wynikająca z wewnątrzwspólnotowego nabycia towarów                                                                                                                                                                                                        | 10812                                                                                                    |
| K_25             | Wysokość podstawy opodatkowania wynikająca z importu towarów rozliczanego zgodnie z art. 33a ustawy, potwierdzona zgłoszeniem celnym lub deklaracją importową, o której mowa w art. 33b ustawy o VAT                                                            | 111010                                                                                                   |
| K_26             | Wysokość podatku należnego wynikająca z importu towarów rozliczanego zgodnie z art. 33a ustawy, potwierdzona zgłoszeniem celnym lub deklaracją importową, o której mowa w art. 33b ustawy o VAT                                                      | 11012                                                                                                    |
| K_27             | Wysokość podstawy opodatkowania wynikająca z importu usług, z wyłączeniem usług nabywanych od podatników podatku od wartości dodanej, do których stosuje się art. 28b ustawy o VAT                                                                                                    | 11110, 11117 (zmiana zwrotna)                                                                            |
| K_28             | Wysokość podatku należnego wynikająca z importu usług, z wyłączeniem usług nabywanych od podatników podatku od wartości dodanej, do których stosuje się art. 28b ustawy o VAT                                                                                               | 11112                                                                                                    |
| K_29             | Wysokość podstawy opodatkowania wynikająca z importu usług nabywanych od podatników podatku od wartości dodanej, do których stosuje się art. 28b ustawy o VAT                                                                                                                                                                                 | 11210, 11119 (zmiana zwrotna)                                                                            |
| K_30             | Wysokość podatku należnego wynikająca z importu usług nabywanych od podatników podatku od wartości dodanej, do których stosuje się art. 28b ustawy o VAT                                                                                                                                       | 11212                                                                                                    |
| K_31             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów, dla których podatnikiem jest nabywca zgodnie z art. 17 ust. 1 pkt 5 ustawy o VAT                                                                                                           | Brak wartości domyślnej                                                                                         |
| K_32             | Wysokość podatku należnego wynikająca z dostawy towarów, dla których podatnikiem jest nabywca zgodnie z art. 17 ust. 1 pkt 5 ustawy o VAT                                                                                                      | Brak wartości domyślnej                                                                                         |
| K_33             | Wysokość podatku należnego od towarów objętych spisem z natury, o którym mowa w art. 14 ust. 5 ustawy o VAT                                                                                                                                                    | Brak wartości domyślnej                                                                                         |
| K_34             | Wysokość zwrotu odliczonej lub zwróconej kwoty wydanej na zakup kas rejestrujących, o którym mowa w art. 111 ust. 6 ustawy o VAT                                                                                                         | Brak wartości domyślnej                                                                                         |
| K_35             | Wysokość podatku należnego od wewnątrzwspólnotowego nabycia środków transportu, wykazana w wysokości podatku należnego z tytułu wewnątrzwspólnotowego nabycia towarów, podlegająca wpłacie w terminie, o którym mowa w art. 103 ust. 3, w związku z ust. 4 ustawy o VAT            | Brak wartości domyślnej                                                                                         |
| K_36             | Wysokość podatku od wewnątrzwspólnotowego nabycia towarów, o których mowa w art. 103 ust. 5aa ustawy, podlegająca wpłacie w terminie, o którym mowa w art. 103 ust. 5a i 5b ustawy o VAT              | Brak wartości domyślnej                                                                                         |
| K_40             | Wartość netto wynikająca z nabycia towarów i usług zaliczanych u podatnika do środków trwałych                                                                                                                                                                     | 20107, 20115                                                                                             |
| K_41             | Wysokość podatku naliczonego przysługującego do odliczenia z podstaw określonych w art. 86 ust. 2 ustawy o VAT, na warunkach określonych w ustawie o VAT wynikająca z nabycia towarów i usług zaliczanych u podatnika do środków trwałych | 20109                                                                                                    |
| K_42             | Wartość netto wynikająca z nabycia pozostałych towarów i usług                                                                                                                                                                                                  | 20207, 20215                                                                                             |
| K_43             | Wysokość podatku naliczonego przysługującego do odliczenia z podstaw określonych w art. 86 ust. 2 ustawy o VAT, na warunkach określonych w ustawie o VAT wynikająca z nabycia pozostałych towarów i usług                                                 | 20209                                                                                                    |
| K_44             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o których mowa w art. 90a–90c oraz art. 91 ustawy o VAT, z tytułu nabycia towarów i usług zaliczanych u podatnika do środków trwałych                                 | 20116                                                                                                    |
| K_45             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o których mowa w art. 90a–90c oraz art. 91 ustawy o VAT, z tytułu nabycia pozostałych towarów i usług                                                                         | 20216                                                                                                    |
| K_46             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o której mowa w art. 89b ust. 1 ustawy o VAT                                                                                                                                           | 30101, 30102 **Uwaga:** w scenariuszu „zaległości” może zostać pobrana kwota z **K_43** lub **K_41**. |
| K_47             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o której mowa w art. 89b ust. 4 ustawy o VAT                                                                                                                                           | 30201, 30202 **Uwaga:** w scenariuszu „zaległości” kwotę można zebrać dla **K_43** lub **K_41**. |

### <a name="create-an-electronic-message-for-jpk-v7m-reporting"></a>Tworzenie wiadomości elektronicznej raportowania JPK-V7M

1. Przejdź do menu **Podatek** \> **Zapytania i raporty** \> **Wiadomości elektroniczne** \> **Wiadomości elektroniczne**.
2. Wybierz **JPK-V7M**, a następnie na skróconej karcie **Wiadomości** wybierz opcję **Nowy**.
3. W oknie dialogowym **Uruchom przetwarzanie** kliknij **OK**.

    ![Okno dialogowe Uruchamianie przetwarzania](media/create-em.jpg)

4. Zostanie utworzona nowa wiadomość elektroniczna. Wprowadź opis i określ datę początkową i końcową okresu, za który chcesz wygenerować raport JPK-V7M.
5. Na skróconej karcie **Dodatkowe pola wiadomości** określ dodatkowe wartości wymagane w części deklaracji raportu V7M.

    ![Skrócona karta Dodatkowe pola wiadomości](media/message-additional-fields.jpg)

6. W dodatkowym polu **CelZlozenia** określ, czy przesyłany raport jest złożeniem deklaracji czy korektą. Dwie wartości są dozwolone:

    - **1** — to złożenie jest pierwszym złożeniem deklaracji za podany okres. Ta wartość jest wartością domyślną.
    - **2** — to złożenie jest korektą deklaracji za podany okres.

Można również określić ręczne wartości następujących elementów deklaracji.

| **Imię i nazwisko** | **Opis (EN)**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | **Opis (PL)**                                                                                                                                                                                                                          |
|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| P_39     | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Wysokość nadwyżki podatku naliczonego nad należnym z poprzedniej deklaracji.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Wysokość nadwyżki podatku naliczonego nad należnym z poprzedniej deklaracji                                                                                                                                                                   |
| P_49     | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym pomniejszająca wysokość podatku należnego. Kwota wykazana w **P_49** nie może być większa niż **P_38** – **P_48**. Jeśli **P_38** – **P_48** jest mniejsze lub równe 0 (zero), należy wykazać **0**.                                                                                                                                                                                                                                                                                                                | Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym pomniejszająca wysokość podatku należnego                                                                                                              |
| P_50     | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Wysokość podatku objęta zaniechaniem poboru. Wartość **P_50** nie może być większa niż **P_38** – **P_48** – **P_49**. Jeśli **P_38** – **P_48** – **P_49** jest mniejsze lub równe 0 (zero) lub większe lub równe **P_50**, należy wykazać **0**.                                                                                                                                                                                                                                                                                                                                                                                            | Wysokość podatku objęta zaniechaniem poboru                                                                                                                                                                                                   |
| P_52     | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym przysługująca do zwrotu w danym okresie rozliczeniowym lub powiększająca wysokość podatku naliczonego do przeniesienia na następny okres rozliczeniowy. W przypadku gdy kwota **P_48** jest większa lub równa **P_38** lub kwota ulgi z tytułu zakupu kas rejestrujących jest wyższa od nadwyżki podatku należnego nad naliczonym - w **P_52** wykazuje się pozostałą kwotę ulgi z tytułu zakupu kas rejestrujących, przysługującą podatnikowi do zwrotu lub do odliczenia od podatku należnego za następne okresy rozliczeniowe. | Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym przysługująca do zwrotu w danym okresie rozliczeniowym lub powiększająca wysokość podatku naliczonego do przeniesienia na następny okres rozliczeniowy |
| P_55     | Zwrot na rachunek VAT, o którym mowa w art. 87 ust. 6a ustawy o VAT: 1-tak: zwrot na rachunek VAT podatnika w terminie 25 dni.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Zwrot na rachunek VAT, o którym mowa w art. 87 ust. 6a ustawy: 1 - tak                                                                                                                                                                        |
| P_60     | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Zaliczenie zwrotu podatku na poczet przyszłych zobowiązań podatkowych.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Wysokość zwrotu do zaliczenia na poczet przyszłych zobowiązań podatkowych                                                                                                                                                                     |
| P_61     | Ciąg (1..240), który musi zostać użyty, jeśli użyte jest **P_60**. Rodzaj przyszłego zobowiązania podatkowego.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Rodzaj przyszłego zobowiązania podatkowego                                                                                                                                                                                                    |
| P_ORDZU  | Ciąg (1.. 240). Uzasadnienie przyczyn złożenia korekty zwrotu VAT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Uzasadnienie przyczyn złożenia korekty                                                                                                                                                                                                        |

### <a name="generate-the-jpk-v7m-report-in-excel-format-for-preview"></a>Wygeneruj raport JPK-V7M w formacie Excel do podglądu

1. Gdy wszystkie dane są gotowe w systemie, wybierz opcję **Generuj raport** na skróconej karcie **Wiadomości**.
2. W oknie dialogowym **Uruchamianie przetwarzania** w polu **Akcja** wybierz opcję **Podgląd w programie Excel**.
3. Kliknij przycisk **OK**.

    ![Okno dialogowe uruchamiania przetwarzania, pole akcji](media/generate-vdek.jpg)

4. Aby uruchomić generowanie raportu w partii, należy określić parametry na skróconej karcie **Uruchamianie w tle**. Po wygenerowaniu raportu jest on dołączany do wiadomości elektronicznej jako plik.
5. Aby obejrzeć plik, wybierz wiadomość elektroniczną, po czym naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony.
6. Na stronie **Załączniki wiadomości** wybierz załącznik, a następnie, w okienku akcji, wybierz **Otwórz**.

### <a name="generate-an-xml-file-in-jpk-v7m-format"></a>Generowanie pliku XML w formacie JPK-V7M

1. Gdy wszystkie dane są gotowe w systemie, wybierz opcję **Generuj raport** na skróconej karcie **Wiadomości**.
2. W oknie dialogowym **Uruchom przetwarzanie** kliknij **OK**.

    ![Skrócona karta Wiadomości, okno dialogowe Uruchamianie przetwarzania](media/generate-xml-vdek.jpg)

3. Aby uruchomić generowanie raportu w partii, należy określić parametry na skróconej karcie **Uruchamianie w tle**.

Po naciśnięciu **OK** w oknie dialogowym powinien pojawić się następujący tekst oświadczenia:

- **Angielski:** "When you generate the VAT declaration you confirm information in the report is true and complete. Your consent will be recorded in the report. Incomplete payment or non-payment of VAT due to the Tax Authority, this declaration is the basis for the issuance of a writ of execution in accordance with the provisions of the enforcement proceedings in the administration. A false or incomplete declaration may result in prosecution in accordance with regulations of fiscal penal code."
- **Polski:** „Wygenerowanie deklaracji VAT oznacza potwierdzenie, że informacje w raporcie są prawdziwe i kompletne. Twoja zgoda zostanie odnotowana w raporcie. W przypadku niewpłacenia w obowiązującym terminie podatku podlegającego wpłacie do urzędu skarbowego lub wpłacenia go w niepełnej wysokości niniejsza deklaracja stanowi podstawę do wystawienia tytułu wykonawczego zgodnie z przepisami o postępowaniu egzekucyjnym w administracji. Za podanie nieprawdy lub zatajenie prawdy i przez to narażenie podatku na uszczuplenie grozi odpowiedzialność przewidziana w przepisach Kodeksu karnego skarbowego”.

Naciskając **OK** na stronie oświadczenia, wyrażasz zgodę na oświadczenie. JPK_VDEK zostanie wygenerowana tylko wtedy, gdy użytkownik wyrazi zgodę na oświadzcenie.

Dziennik akcji jest związany z informacjami dziennika wiadomości elektronicznych dotyczącymi użytkownika, który wygenerował JPK_VDEK i wykonał inne akcje z wiadomością elektroniczną.

Po wygenerowaniu pliku XML raportu JPK_V7M jest on dołączany do wiadomości elektronicznej. Aby obejrzeć plik, wybierz wiadomość elektroniczną, po czym naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony. Na stronie **Załączniki wiadomości** wybierz załącznik, a następnie, w okienku akcji, wybierz **Otwórz**.

### <a name="change-the-status-of-the-electronic-message"></a>Zmienianie stanu wiadomości elektronicznej

Po zakończeniu pracy z raportem można zmienić stan na **Zgłoszone JPK_VDEK** (**Reported JPK-V7M**). Wiadomości elektronicznej w tym stanie nie można usunąć. W razie konieczności można zmienić stan z powrotem na **Wygenerowane JPK_VDEK**.

Aby zmienić stan wiadomości elektronicznej, na skróconej karcie **Wiadomości** wybierz opcję **Aktualizuj stan** \> **Nowy stan**.

## <a name="split-payment-mpp-marker"></a>Marker podzielonej płatności (MPP)

W raporcie JPK-V7M wprowadzono marker **MPP** zarówno dla ewidencji sprzedaży, jak i ewidencji zakupów.

Jeśli firma wykonuje operacje, dla których należy zastosować procedurę podzielonej płatności, należy użyć funkcji **„Podzielona płatność”**.

Gdy jest używana funkcja podzielonej płatności, nie trzeba wykonywać żadnej specjalnej konfiguracji, aby zgłosić marker **MPP** w JPK-V7M. Do identyfikacji markera **MPP** jest używany następujący algorytm:

- System zapewnia kontrolę parametrów **Podzielona płatność** i **Dobrowolna podzielona płatność** dla transakcji odbiorcy, która jest związana z fakturą sprzedaży. Jeśli wybrano parametr **Podzielona płatność**, a parametr **Dobrowolna podzielona płatność** jest wyczyszczony, powiązana faktura zostanie zaraportowana przy użyciu znacznika **MPP**.
- System zapewnia kontrolę parametrów **Podzielona płatność** i **Dobrowolna podzielona płatność** dla transakcji dostawcy, która jest związana z fakturą od dostawcy. Jeśli wybrano parametr **Podzielona płatność**, a parametr **Dobrowolna podzielona płatność** jest wyczyszczony, powiązana faktura zostanie zaraportowana przy użyciu znacznika **MPP**.

## <a name="reporting-of-overdue-customer-invoices"></a>Raportowanie zaległych faktur dla odbiorcy

Wersja 72.150 konfiguracji **Format JPK-V7M XML (PL)**, podobnie jak nowsze wersje, obsługuje raportowanie zaległych faktur dla odbiorcy w przypadku stosowania lokalnej polskiej funkcji [Zaległa kwota podatku VAT stanowiąca zadłużenie](emea-pol-sales-tax-reports.md#allowance-for-bad-debts).

### <a name="business-requirement"></a>Wymagania biznesowe

- Jeśli procedura jest stosowana przez firmę, element **\<P_68\>** części deklaracji musi raportować wysokość podstawy opodatkowania dla zaległych faktur w okresie raportu (czyli transakcje, które zostały zaksięgowane w celu odliczenia podatku VAT z tytułu wystawionych faktur, które nie zostały zapłacone w ciągu 150 dni od terminu płatności).
- Jeśli procedura jest stosowana przez firmę, element **\<P_69\>** części deklaracji musi raportować wysokość VAT dla zaległych faktur w okresie raportu (czyli transakcje, które zostały zaksięgowane w celu odliczenia podatku VAT z tytułu wystawionych faktur, które nie zostały zapłacone w ciągu 150 dni od terminu płatności).
- Jeśli procedura jest stosowana przez firmę, ta transakcja musi być raportowana dla zaległych faktur w okresie, w którym minęło 150 dni od terminu płatności. Należy wpisać informacje o odbiorcy z oryginalnej faktury oraz kwotę, która ma znak minus (–).
- Jeśli procedura jest stosowana przez firmę, ta transakcja musi być raportowana dla zapłaconych zaległych faktur w okresie, gdy zaległa faktura została zapłacona. Należy wpisać wszystkie informacje o odbiorcy z oryginalnej faktury oraz kwotę, która ma znak plus (+).
- Jeśli zaległe i opłacone zaległe transakcje zaległe są w tym samym okresie raportu, a procedura jest stosowana przez firmę, można opcjonalnie raportować obie transakcje w ewidencji sprzedaży. W tym przypadku nie są raportowane elementy **\<P_68\>** i **\<P_69\>** części deklaracji.

### <a name="supported-business-user-scenario-in-finance"></a>Obsługiwany scenariusz użytkownika biznesowego w module Finance

Jeśli istnieje zaległa faktura dla odbiorcy, faktura, która jest wystawiana odbiorcy, może przejść trzy etapy:

1. Faktura jest wystawiana odbiorcy, księgowane są transakcje podatkowe, a faktura jest uwzględniana w **JPK** \> **Ewidencja** \> **SprzedazWiersz** jak zwykle, zgodnie z konfiguracją podatku i konfiguracją markerów.
2. Jeśli faktura nie zostanie zapłacona w ciągu 150 dni od terminu płatności, firma może zastosować zadanie okresowe [Zaległa kwota podatku VAT stanowiąca zadłużenie](emea-pol-sales-tax-reports.md#allowance-for-bad-debts), przechodząc do **Rozrachunki z odbiorcami** \> **Zadania okresowe** \> **Zaległa kwota podatku VAT stanowiąca zadłużenie**. Transakcje podatkowe generowane przez to zadanie są odzwierciedlane w raporcie JPK-V7M. Zawarte są następujące informacje:

    - Uwzględnione są wszystkie informacje o odbiorcy z oryginalnej faktury zaksięgowanej w etapie 1.
    - Kwoty są raportowane w tych samych elementach **K_\** _, co w oryginalnej fakturze, ale ze znakiem ujemnym.
    - Stosowane są te same markery, które zastosowano w oryginalnej fakturze.
    - Jest stosowany marker _ *\<KorektaPodstawyOpodt\>**.

     Ponadto kwota podstawy i kwota podatku z tej faktury (dokument wewnętrzny) są uwzględniane i zgłaszane w elementach **P_68** i **P_69** części deklaracji raportu.

3. Jeśli faktura zostanie zaksięgowana po wystąpieniu obu etapów 1 i 2, firma musi ponownie zastosować zadanie okresowe **Zaległa kwota podatku VAT stanowiąca zadłużenie** w okresie, w którym faktura została zapłacona. Wynikowe transakcje podatkowe są odzwierciedlane w raporcie JPK-V7M. Zawarte są następujące informacje:

    - Uwzględnione są wszystkie informacje o odbiorcy z oryginalnej faktury zaksięgowanej w etapie 1.
    - Kwoty są raportowane w tych samych elementach **K_\** _, co w oryginalnej fakturze, ale ze znakiem dodatnim.
    - Stosowane są te same markery, które zastosowano w oryginalnej fakturze
    - Jest stosowany marker _ *\<KorektaPodstawyOpodt\>**.

    Kwota podstawy i kwota podatku z tej faktury (dokument wewnętrzny) **nie** są uwzględniane i zgłaszane w elementach **P_68** i **P_69** części deklaracji raportu.

> [!IMPORTANT]
> Jeśli etapy 2 i 3 występują w tym samym okresie raportu, elementy **P_68** i **P_69** części deklaracji raportu nie podlegają zmianie.

## <a name="report-ro-and-fp-document-types-for-retail-operations"></a>Raportowanie typów dokumentów RO i FP dla operacji handlu detalicznego

Wersja 83.169 konfiguracji **Format JPK-V7M XML (PL)**, podobnie jak nowsze wersje, obsługuje raportowanie typów dokumentów **RO** i **FP** dla operacji handlu detalicznego w przypadku stosowania funkcji odbiorcy w przypadku stosowania funkcji [Uzupełniającej faktury sprzedaży w handlu detalicznym w Polsce](emea-pol-vdek.md).

### <a name="business-requirements"></a>Wymagania biznesowe

Poniższe zasady raportowania faktur sprzedaży dla operacji handlu detalicznego są oparte na wyjaśnieniach opublikowanych w sekcji Pytania i odpowiedzi oficjalnego portalu podatkowego polskiego Ministerstwa Finansów:

- Wszystkie paragony fiskalne, które są drukowane i wydawane odbiorcom, muszą być zagregowane i zgłoszone jako dokumenty typu **RO** (faktura zbiorcza). Sprzedaż niekrajowym odbiorcom musi być wykluczona z agregacji i zgłaszana jako zwykłe faktury (bez markera typu dokumentu). Należy wykonać agregację dla okresu raportu. Dokumenty sprzedaży raportowane jako dokumenty typu **RO** (faktura zbiorcza) nie podlegają markerom **GTU**. Sprzedaż krajowa, która jest agregowana na potrzeby raportowania jako dokumenty podlegające opodatkowaniu typu **RO** musi być także raportowana jako osobne dokumenty podlegające opodatkowaniu typu **FP**, jeśli odbiorca zażąda faktury za tę sprzedaż. Faktury oznaczone jako dokumenty typu **FP** muszą być wykluczane z sum w **SprzedazCtrl** i wszystkich powiązanych wartościach **P_\**_ części deklaracji. Dokumenty sprzedaży, które są raportowane jako dokumenty typu _* FP** podlegają markerom **GTU**.

### <a name="initial-assumptions-for-the-reporting-of-fiscal-documents-in-a-jpk-v7m"></a>Wstępne założenia dotyczące zgłaszania dokumentów fiskalnych w JPK-V7M

- Wszystkie dokumenty pochodzące z kasy fiskalnej (POS) są opodatkowane.
- Informacje o paragonach fiskalnych przetwarzanych w kasie fiskalnej są poprawnie odzwierciedlone w następujących tabelach bazy danych systemu:

    - RetailTransactionTable
    - RetailTransactionSalesTrans
    - RetailTransactionTaxTrans

- Jeśli odbiorca podał numer VAT do paragonu fiskalnego w kasie fiskalnej, jest on przechowywany w tabeli RetailTransactionFiscalCustomer.SerializedData.
- Wszystkie paragony fiskalne i wstępnie zagregowane dokumenty fiskalne zaksięgowane za pośrednictwem zestawienia sprzedaży detalicznej, które muszą zostać zagregowane na potrzeby raportowania, są księgowane w arkuszu faktur dla odbiorcy ze stanem **Dokument fiskalny** lub **Dokument fiskalny przekonwertowany na fakturę**.
- Jeśli faktura została utworzona w kasie fiskalnej, jest ona poprawnie odzwierciedlona w tabeli RetailTransactionSupplementaryInvoice.
- Jeśli paragon fiskalny został przekonwertowany z dokumentu fiskalnego na fakturę, ma stan faktury **Dokument fiskalny przekonwertowany na fakturę** w arkuszu faktur dla odbiorcy. (Założenie to dotyczy tylko dokumentów fiskalnych, które nie są wstępnie zagregowane).
- Tylko zaksięgowane transakcje detaliczne typu **Sprzedaż** są traktowane jako faktury sprzedaży detalicznej do celów raportowania jako dokumenty typu **FP**.
- Specyficzne scenariusze, takie jak scenariusz „karty upominkowej”, są obecnie poza zakresem.

### <a name="supported-business-user-scenario-in-finance"></a>Obsługiwany scenariusz użytkownika biznesowego w module Finance

Aby raportować typy dokumentów typu **RO** i **FP** za operacje handlu detalicznego, należy skorzystać z następujących parametrów w grupie parametrów **Oznaczenie sprzedaży właściwe dla sprzedaży detalicznej** klasy wykonywalnej **Wygenerowanie JPK_V7M** (**EMGenerateJPKVDEKReportController_PL**) (**Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Ustawienia klasy wykonywalnej**):

- Pole wyboru **Zagregowane dokumenty fiskalne** uaktywnia rekordy **Kryteria zbierania faktur dla odbiorcy na potrzeby agregacji (RO — faktury zbiorcze)**, które są uwzględniane w zbieraniu i agregowaniu paragonów fiskalnych, które muszą być raportowane jako dokumenty typu **RO**.
- Pole wyboru **Zgłoś faktury z kasy fiskalnej** gromadzi faktury sprzedaży detalicznej, które mają datę faktury w okresie raportu i zgłasza je jako dokumenty typu **FP**.
- Pole wyboru **Zgłoś dokument fiskalny przekonwertowany na fakturę** zbiera faktury z tabeli CustInvoiceJour, które mają stan **Dokument fiskalny przekonwerterowany na fakturę** i **FiscalDocDate_PL** w okresie raportu oraz zgłasza je jako dokumenty typu **FP**.

#### <a name="aggregate-fiscal-documents-parameter"></a>Parametr zagregowanych dokumentów fiskalnych

Domyślnie pole wyboru **Zagregowane dokumenty fiskalne** nie jest zaznaczone. W takim przypadku system nie agreguje żadnych dokumentów. Dokumenty są raportowane jako standardowe dokumenty, w których nie jest stosowany żaden typ dokumentu. W związku z tym raport działa tak, jak działał przed tą zmianą.

Jeśli zaznaczono pole wyboru **Zagregowane dokumenty fiskalne**, faktury krajowe mające stan **Dokument fiskalny** lub **Dokument fiskalny przekonwertowany na fakturę** oraz wartość **Data ewidencji VAT**, która przypada w okresie raportu, są raportowane jako jeden zagregowany dokument typu **RO** za okres raportu. Użytkownik definiuje specyficzne dla firmy kryteria krajowych dokumentów fiskalnych, które muszą być zagregowane przy użyciu rekordów **Kryteria zbierania faktur dla odbiorcy na potrzeby agregacji (RO — faktury zbiorcze)**.

Jeśli raport zawiera zagregowany dokument typu **RO**, ma on następujące pola nagłówka.

| **Tag raportowania**  | **Wartość**                             |
|--------------------|---------------------------------------|
| KodKrajuNadaniaTIN | PL                                    |
| NrKontrahenta      | BRAK                                  |
| NazwaKontrahenta   | Sprzedaz paragonowa                   |
| DowodSprzedazy     | ROyyyyMMdd                            |
| DataWystawienia    | Ostatnia data okresu raportu. |
| DataSprzedazy      | Ostatnia data okresu raportu. |
| TypDokumentu       | RO                                    |

#### <a name="report-retail-pos-invoices-parameter"></a>Parametry raportowania faktur z kasy fiskalnej

Domyślnie pole wyboru **Raportuj faktury z kasy fiskalnej** jest wyczyszczone. Po wybraniu tej opcji system gromadzi faktury sprzedaży detalicznej spełniające następujące kryteria:

- W tabeli RetailTransactionSupplementaryInvoice musi znajdować się faktura sprzedaży detalicznej dla transakcji handlu detalicznego w tabeli RetailTransactionTable.
- Wartość **RetailTransactionTable.Type** musi być równa wartości **RetailTransactionType::Sales**.
- Wartość **RetailTransactionTable.entryStatus** musi być równa **RetailEntryStatus::Posted**, a pole **RetailTransactionTable.StatementId** nie może być puste.
- Data faktury (**RetailTransactionSupplementaryInvoice.InvoiceDate**) przypada w okresie raportu.

Pola faktur z kasy fiskalnej z poniższej tabeli muszą być wypełnione.

| **Tag raportowania**  | **Wartość**                                                                                                           |
|--------------------|---------------------------------------------------------------------------------------------------------------------|
| KodKrajuNadaniaTIN | PL                                                                                                                  |
| NrKontrahenta      | „BRAK” lub RetailTransactionFiscalCustomer.SerializedData                                                            |
| NazwaKontrahenta   | Nazwa odbiorcy z danych głównych odbiorcy (RetailTransactionSupplementaryInvoice.AccountNum) lub „BRAK” |
| DowodSprzedazy     | RetailTransactionSupplementaryInvoice.InvoiceId                                                                     |
| DataWystawienia    | RetailTransactionSupplementaryInvoice.InvoiceDate                                                                   |
| DataSprzedazy      | RetailTransactionSalesTrans.TransDate                                                                               |
| TypDokumentu       | FP                                                                                                                  |

Pola tabeli SAFTTaxTransByReportingCode_PL są wypełniane na podstawie następujących źródeł danych.

| **Nazwa tabeli**                        | **Nazwy pól**                                                                                    |
|---------------------------------------|----------------------------------------------------------------------------------------------------|
| RetailTransactionTable                | Typ, EntryStatus, StatementId, kanał, sklep, Terminal, TransactionId                            |
| RetailTransactionTaxTrans             | TaxCode, TaxPercentage, TaxBaseAmount, kwota, IsExempt, kanał, StoreId, Terminal, TransactionId |
| RetailTransactionSupplementaryInvoice | InvoiceId, InvoiceDate, AccountNum, CustInvoiceJour, kanał, sklep, Terminal, TransactionId       |
| RetailTransactionSalesTrans           | TaxGroup, TaxItemGroup, TransDate, waluta, kanał, sklep, TerminalId, TransactionId             |
| RetailTransactionFiscalCustomer       | SerializedData, kanał, sklep, Terminal, TransactionId                                            |

#### <a name="report-fiscal-document-converted-to-invoice-parameter"></a>Parametry raportowania dokumentu fiskalnego przekonwertowanego na fakturę

Domyślnie pole wyboru **Zgłoś dokument fiskalny przekonwertowany na fakturę** nie jest zaznaczone. W takim przypadku, jeśli zbiór transakcji podatkowych i powiązanych z nimi faktur dla odbiorcy został zagregowany i zgłoszony jako dokumenty typu **RO**, są one wykluczone ze zbioru transakcji raportowanych domyślnie.

Gdy pole wyboru **Zgłoś dokument fiskalny przekonwertowany na fakturę** jest zaznaczone, system zbiera faktury z tabeli CustInvoiceJour przy użyciu tych samych rekordów **Kryteria zbierania faktur dla odbiorcy na potrzeby agregacji**, które są zdefiniowane dla faktur krajowych do agregacji. Stosowane są także następujące kryteria dodatkowe:

- Wartość **CustInvoiceJour_PL.FiscalDocState_PL** musi być równa wartości pola **Dokument fiskalny przekonwertowany na fakturę**.
- **CustInvoiceJour_PL.FiscalDocDate_PL** musi być w okresie raportu.

Podczas wstępnego przetwarzania te faktury są traktowane jako faktury standardowe. Jedyną różnicą jest to, że ich typ dokumentu jest ustawiany na **FP**.

## <a name="generate-the-jpk-v7m-report-for-part-of-a-month"></a>Generowanie raportu JPK-V7M za część miesiąca

Wersja 72.158 konfiguracji **Format JPK-V7M XML (PL)**, podobnie jak nowsze wersje, obsługuje raportowanie JPK-V7M za okresy krótsze niż pełny miesiąc.

Aby wygenerować raport JPK-V7M za okres krótszy niż pełny miesiąc, na stronie **Wiadomości elektroniczne** (**Podatek** \> **Zapytania i raporty** \> **Wiadomości elektroniczne** \> **Wiadomości elektroniczne**) należy użyć pól **Data początkowa** i **Data końcowa**, aby zdefiniować interwał dat, za który ma zostać wygenerowany raport JPK-V7M. Te daty muszą należeć do tego samego miesiąca kalendarzowego.

W przypadku generowania raportu JPK-V7M w formacie XML za okres krótszy niż pełny miesiąc pojawi się ostrzeżenie, że raport jest generowany za mniej niż pełny miesiąc i nie będzie mógł zostać przesłany do urzędu. Raport będzie zawierał także następujące informacje wskazujące, że nie jest za pełny miesiąc:

- Tag **\<Miesiac\>** będzie zawierać informacje o interwale dat, za który jest generowany raport.
- Tag **\<P_\*\>** części **Deklaracja** raportu zawiera obliczone wartości reprezentujące agregację kwot z części **SprzedazWiersz** i **ZakupWiersz** raportu. Wartości w tym tagu zostaną zaokrąglone do dwucyfrowej wartości dziesiętnej, ale nie wartości całkowitej.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]