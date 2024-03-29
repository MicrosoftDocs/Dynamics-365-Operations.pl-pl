---
title: Przygotowanie do raportowania JPK-V7M
description: Ten artykuł zawiera informacje o tym, jak skonfigurować deklarację VAT z rejestrami (znanymi również jako JPK-V7M, VDEK) w Polsce.
author: AdamTrukawka
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: atrukawk
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
ms.openlocfilehash: 1b263209f69dc41405993fb5ed866d0b2cbb6113
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274572"
---
# <a name="prepare-for-jpk-v7m-reporting"></a>Przygotowanie do raportowania JPK-V7M

[!include [banner](../includes/banner.md)]

Rozwiązanie obsługujące raportowanie JPK-V7M opiera się na funkcji [obsługi wiadomości elektronicznych](../general-ledger/electronic-messaging.md). Ta funkcja zapewnia elastyczne podejście do konfigurowania i obsługiwania procesów raportowania.

Poniższe zadania przygotowują aplikację Microsoft Dynamics 365 Finance do tworzenia raportu JPK_V7M:

- [Importowanie i konfigurowanie konfiguracji raportowania elektronicznego (ER)](#configurations-vdek).
- [Konfigurowanie parametrów specyficznych dla aplikacji](#application-specific-parameters-vdek).
- [Importowanie pakietu jednostek danych zawierającego wstępnie zdefiniowaną konfigurację wiadomości elektronicznych](#import-data-entities-vdek).
- [Konfigurowanie parametrów księgi głównej](#general-ledger-parameters-vdek).
- [Zapisywanie parametrów klasy wykonywalnej dla wiadomości elektronicznych](#executable-class-parameters-vdek).
- [Konfigurowanie ról zabezpieczeń na potrzeby przetwarzania wiadomości elektronicznych](#security-roles-vdek).
- [Konfigurowanie kodu urzędu na potrzeby przetwarzania wiadomości elektronicznych](#office-code-vdek).
- [Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej](#sales-tax-reporting-codes-vdek).

## <a name="import-and-set-up-er-configurations"></a><a id="configurations-vdek"></a>Importowanie i konfigurowanie konfiguracji ER

Aby przygotować Finance do raportowania JPK-V7M, musisz zaimportować następujące konfiguracje ER.

| Nazwa konfiguracji ER             | Typ | opis |
|-----------------------------------|------|-------------|
| Standardowy plik audytu (SAF-T)       | Model | Wspólny model ER dla jednolitych plików kontrolnych. |
| Mapowanie modelu jednolitego pliku kontrolnego | Mapowanie modelu | Mapowanie modelu definiujące źródła danych dla raportów polskiego jednolitego pliku kontrolnego (JPK). |
| Format XML JPK-V7M (PL)           | Format (eksportowanie) | Format XML dostarczający plik, którego okresowego przesyłania wymaga polskie Ministerstwo Finansów. |
| Format Excel JPK-V7M (PL)         | Format (eksportowanie) | Format programu Excel służący do podglądu informacji, które będą raportowane w formacie XML. |

Importowanie ostatniej wersji tych konfiguracji. Opis wersji zazwyczaj zawiera numer artykułu z bazy wiedzy Microsoft Knowledge Base (KB), który wyjaśnia zmiany wprowadzone w wersji konfiguracji systemu. Narzędzie wyszukiwanie problemów w [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/v2) umożliwia znalezienie artykułu z bazy wiedzy na podstawie numeru.

Aby uzyskać więcej informacji na temat pobierania konfiguracji modułu ER z globalnego repozytorium Microsoft, zapoznaj się z tematem [Pobieranie konfiguracji ER z repozytorium globalnego](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

> [!NOTE]
> Po zaimportowaniu wszystkich konfiguracji ER z poprzedniej tabeli należy zmienić ustawienie opcji **Ustawienie domyślne mapowanie modelu** na **Tak** w przypadku konfiguracji **Mapowanie jednolitych plików kontrolnych** na stronie **Konfiguracje**.
>
> ![Wartość domyślna opcji mapowania modelu ustawiona na Tak w przypadku konfiguracji mapowania modelu standardowego modelu pliku inspekcji](media/default-mm.jpg)

## <a name="set-up-application-specific-parameters"></a><a id="application-specific-parameters-vdek"></a>Konfigurowanie parametrów specyficznych dla aplikacji

W zależności od danych transakcji podatkowych, wartości niektórych elementów (znaczników) w raporcie JPK-V7M można zdefiniować na potrzeby raportowania. Aby można było zdefiniować wartości tych elementów, musi być wystarczająco dużo danych transakcyjnych. Dlatego należy skonfigurować odpowiednią liczbę kodów podatków, grup podatków i grup podatków dla towaru, aby rozróżnić transakcje podatkowe dla wszystkich parametrów (elementów) wprowadzonych w raporcie JPK-V7M. Format JPK-V7M zawiera parametry (pola) specyficzne dla aplikacji, które mogą być używane do definiowania wartości tych elementów w raporcie.

> [!NOTE]
> Zaleca się włączenie tej funkcji: **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** w obszarze roboczym **Zarządzanie funkcjami**. Gdy ta funkcja jest włączona, parametry skonfigurowane dla wcześniejszej wersji formatu raportowania elektronicznego automatycznie stają się dostępne dla nowszej wersji tego samego formatu. Jeśli ta funkcja nie jest włączona, należy skonfigurować parametry specyficzne dla aplikacji jawnie dla każdej wersji formatu. Funkcja **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** jest dostępna w obszarze roboczym **Zarządzanie funkcjami** w aplikacji Finance w wersji 10.0.23. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji parametrów formatu raportowania elektronicznego dla każdej firmy, zobacz temat [Konfigurowanie parametrów formatu raportowania elektronicznego według firmy](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Format zawiera następujące pola wyszukiwania konfiguracji:

| Imię i nazwisko                          | opis | Wpływ |
|-------------------------------|-------------|--------|
| ImportSelector                | Oznaczenie, które jest związane z podatkiem naliczonym od przywozu towarów, w tym towarów opodatkowanych zgodnie z artykułem 33a ustawy o VAT | To pole wyszukiwania służy do definiowania wartości markera **IMP** dla dokumentów zakupu. |
| ProceduralMarkingsSelector    | Oznaczenia związane z procedurami | To pole wyszukiwania służy do definiowania wartości następujących markerów dokumentów sprzedaży: **SW**, **EE**, **TP**, **TT-WNT**, **TT_D**, **I_42**, **I_63**, **B_SPV**, and **B_SPV_DOSTAWA**. |
| ServiceDeliverySelector       | Wskaźnik związany z dostawą i świadczeniem usług | To pole wyszukiwania służy do definiowania wartości wszystkich markerów **GTU_\**_ (od _* GTU_1** do **GTU_13**) dla dokumentów sprzedaży. |
| DeclarationMarkersSelector    | Markery z części deklaracji dla transakcji podatkowych | To pole wyszukiwania służy do definiowania markerów **P_65** i **P_67** części deklaracji, na podstawie informacji zawartych w dokumencie. |
| ZakupVAT_MarzaSelector        | Kwota zakupu towarów i usług od innych podatników na bezpośrednią korzyść turystów oraz ilość towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą, które są opodatkowane na podstawie marży, zgodnie z artykułem 120 ustawy o VAT | To pole wyszukiwania służy do definiowania markera **ZakupVAT_Marza** dla dokumentów zakupu. |
| SalesDocumentTypesSelector    | Oznaczenie typu dokumentu sprzedaży | To pole wyszukiwania służy do definiowania typów dokumentu sprzedaży **FP**, **RO** i **WEW**. |
| SprzedazVAT_MarzaSelector     | Wartość sprzedaży brutto dostaw towarów i usług, które są opodatkowane na podstawie marży, zgodnie z artykułami 119 i 120 ustawy o podatku VAT | To pole wyszukiwania służy do definiowania markera **SprzedazVAT_Marza** dla dokumentów sprzedaży. |
| PurchaseDocumentTypesSelector | Oznaczenie typu dokumentu zakupu | To pole wyszukiwania służy do definiowania typów dokumentu zakupu **MK**, **VAT_RR** i **WEW**. |

1. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
2. Na stronie **Konfiguracje** rozwiń węzeł **Standardowy plik audytu (SAF-T)** i wybierz opcję **Format XML JPK-V7M (PL)**.
3. W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.

    ![Przycisk Ustawienia w grupie Parametry specyficzne dla aplikacji na karcie Konfiguracje](media/setup-app-spec-params.jpg)

4. Na stronie **Parametry specyficzne dla aplikacji** wybierz najnowszą wersję formatu, dla którego chcesz zdefiniować warunki.
5. Na skróconej karcie **Wyszukiwania** wybierz poszczególne wyszukiwania i zdefiniuj odpowiednie warunki dla nich.
6. Na skróconej karcie **Warunki** określ, które kody podatków lub inne dostępne kryteria muszą odpowiadać określonemu wynikowi wyszukiwania. 

    Jeśli warunki są zdefiniowane w jednym wierszu, system generalnie zastosuje je do źródłowej transakcji podatkowej za pomocą operatora **AND**. Jeśli warunki muszą być zastosowane za pomocą operatora **OR**, należy je zdefiniować w oddzielnych wierszach. Gdy transakcja podatkowa z okresu raportu spełnia warunek z listy, dla powiązanego dokumentu zostanie zgłoszony powiązany marker z wyniku wyszukiwania. Aby uzyskać więcej informacji o ustawieniach poszczególnych pól wyszukiwania, przejdź do tego artykułu.

7. Po zakończeniu konfigurowania warunków w polu **Stan** wybierz opcję **Zakończono**, a następnie zapisz konfigurację.

    ![Stanowe pole ustawione na Zakończono](media/complete-app-spec-params.jpg)

Konfigurację parametrów specyficznych dla aplikacji można łatwo wyeksportować z jednej wersji raportu i zaimportować do innej. Możesz także wyeksportować konfigurację z jednego raportu i zaimportować ją do innego raportu, pod warunkiem, że oba raporty mają taką samą strukturę pól odnośników.

> [!NOTE]
> Zaleca się włączenie tej funkcji: **Podczas importowania wyrównaj parametry specyficzne dla aplikacji raportowania elektronicznego** w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja jest dostępna od aplikacji Finance w wersji 10.0.24. Po jej włączeniu, jeśli struktura importowanych parametrów specyficznych różni się od struktury odpowiedniego źródła danych typu wyszukiwania w docelowym formacie ER, który został wybrany do importu, w niektórych przypadkach importowanie zakończy się powodzeniem. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji parametrów formatu raportowania elektronicznego dla każdej firmy, zobacz temat [Konfigurowanie parametrów formatu raportowania elektronicznego według firmy](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md). 

### <a name="import-transactions-importselector"></a>Importuj transakcje (ImportSelector)

| Nazwa           | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------------|------------|------------|------------------|------------------|
| ImportSelector | Import | Import | Oznaczenie, które jest związane z podatkiem naliczonym od przywozu towarów, w tym towarów opodatkowanych zgodnie z artykułem 33a ustawy o VAT | Oznaczenie dotyczące podatku naliczonego z tytułu importu towarów, w tym importu towarów rozliczanego zgodnie z art. 33a ustawy |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kody podatków
- Grupa podatków
- Identyfikator konta dostawcy
- Grupa dostawców

Zdefiniuj warunki na podstawie głównych źródeł danych bieżącej firmy, aby określić, który dokument zakupu musi zostać zgłoszony z wartością **1** w elemencie **\<IMP\>** pod tagiem **\<ZakupWiersz\>**.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **ImportTransaction**.

| Imię i nazwisko     | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------|------------|------------|------------------|------------------|
| Import   | Import | Import | Oznaczenie, które jest związane z podatkiem naliczonym od przywozu towarów, w tym towarów opodatkowanych zgodnie z artykułem 33a ustawy o VAT | Oznaczenie dotyczące podatku naliczonego z tytułu importu towarów, w tym importu towarów rozliczanego zgodnie z art. 33a ustawy |
| Inne     | Inna | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="procedural-markings-proceduralmarkingsselector"></a>Oznaczenia dotyczące procedur (ProceduralMarkingsSelector)

| Imię i nazwisko                       | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------------------------|------------|------------|------------------|------------------|
| ProceduralMarkingsSelector | Oznaczenia dotyczące procedur | Oznaczenia dotyczące procedur | Oznaczenia związane z procedurami | Oznaczenia dotyczące procedur |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do konfigurowania warunków:

- Kody podatków
- Grupa podatków
- Identyfikator konta odbiorcy
- Grupa odbiorców
- Identyfikator konta dostawcy
- Grupa dostawców

Warunki zdefiniowane w obszarach **Identyfikator konta odbiorcy** i **Grupa klientów** są stosowane niezależnie od warunków zdefiniowanych w grupach **Identyfikator konta dostawcy** i **Grupa dostawców**. Ponadto warunki zdefiniowane w pole **Identyfikator konta dostawcy** i **Grupa dostawców** są stosowane tylko do transakcji zaksięgowanych w zakresie, których dotyczą scenariusza odwrotnych zmian zakresu. Dlatego podczas określania warunków dla pola **Identyfikator konta dostawcy** i **Grupa dostawców** należy określić wartość **\*Puste\*** w kolumnie **Identyfikator konta klienta** i w kolumnie warunków **Grupa klientów**.

To pole wyszukiwania definiuje warunki oparte na głównych źródłach danych bieżącej firmy. Warunki te dają w wyniku marker **1** dla odpowiadającego mu elementu z listy oznaczeń, które są związane z procedurami pod tagiem **\<SprzedazWiersz\>**. Można zaznaczyć więcej niż jedno oznaczenie dla tego samego rekordu należnego podatku VAT. Dlatego, jeśli firma musi zgłosić odmienne oznaczenia, muszą być zdefiniowane odrębne warunki.

**Oznaczenia proceduralne** nie są wymagane w przypadku dokumentów typu **RO** (wewnętrzny dokument podsumowujący) (tag **\<TypDokumentu\>** pod tagiem **\<SprzedazWiersz\>**).

W poniższej tabeli przedstawiono wyniki wyszukiwania (oznaczenia) dla **ProceduralMarkingsSelector**.

| Imię i nazwisko           | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------------|------------|------------|------------------|------------------|
| SW (*tylko dla okresów raportowania do 1 lipca 2021*) | Sprzedaż wysyłkowa | Sprzedaży wysyłkowej | Dostawa w ramach sprzedaży wysyłkowej z terytorium kraju, o której mowa w art. 23 ustawy o VAT | Dostawa w ramach sprzedaży wysyłkowej z terytorium kraju, o której mowa w art. 23 ustawy |
| EE (*tylko dla okresów raportu do 1 stycznia 2022*) | Telekomunikacja | Usługi telekomunikacyjne | Świadczenie usług telekomunikacyjnych, nadawczych i elektronicznych, o których mowa w art. 28k ustawy o VAT | Świadczenie usług telekomunikacyjnych, nadawczych i elektronicznych, o których mowa w art. 28k ustawy |
| TP             | Istniejące powiązania między nabywcą a dokonującym dostawy | Istniejące powiązania między nabywcą a dokonującym | Istniejące powiązania pomiędzy kupującym a dostawcą towarów lub usługodawcą, o których mowa w art. 32 ust. 2 pkt 1 ustawy o VAT. Wyjątkiem jest przypadek dostaw towarów i świadczenia usług, w których stosunek między nabywcą a dostawcą usług wynika wyłącznie z powiązania ze Skarbem Państwa lub jednostkami samorządu terytorialnego lub ich stowarzyszeniami. | Istniejące powiązania między nabywcą a dokonującym dostawy towarów lub usługodawcą, o których mowa w art. 32 ust. 2 pkt 1 ustawy. Z wyjątkiem sytuacji, gdy jest dostawą towarów i świadczenia usług, gdy powiązania między nabywcami a dokonującym dostawy towarów lub usługodawcą z dostawami ze Skarbem Państwa lub jednostkami samorządu ich związkami. |
| TT_WNT         | Wewnątrzwspólnotowe nabycie w ramach transakcji trójstronnej | Wewnątrzwspólnotowe nabycie w ramach transakcji trójstronnej | Wewnątrzwspólnotowe nabycie towarów dokonane przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy o VAT | Wewnątrzwspólnotowe nabycie towarów dokonane przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy |
| TT_D           | Dostawa towarów poza terytorium Polski w ramach transakcji trójstronnej | Dostawa towarów poza terytorium kraju w ramach transakcji trójstronnej | Dostawa towarów poza terytorium kraju dokonana przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy o VAT | Dostawa towarów poza terytorium kraju dokonana przez drugiego w kolejności podatnika VAT w ramach transakcji trójstronnej w procedurze uproszczonej, o której mowa w dziale XII rozdziale 8 ustawy |
| I_42           | Procedura celna 42 (import) | Procedura celna 42 (import) | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 42 (import) | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 42 (import) |
| I_63           | Procedura celna 63 (import) | Procedura celna 63 (import) | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 63 (import) | Wewnątrzwspólnotowa dostawa towarów następująca po imporcie tych towarów w ramach procedury celnej 63 (import) |
| B_SPV          | Transfer z artykułu 8A, ustęp 1 ustawy o VAT | Transfer z art. 8a ust. 1 ustawy | Transfer bonu jednego przeznaczenia dokonany przez podatnika działającego własnym imieniu, opodatkowany zgodnie z art. 8a ustęp 1 ustawy o VAT | Transfer bonu jednego przeznaczenia dokonany przez podatnika działającego we własnym imieniu, opodatkowany zgodnie z art. 8a ust. 1 ustawy |
| B_SPV_DOSTAWA  | Dostawa towarów oraz świadczenie usług, których dotyczy Bon jednego przeznaczenia (artykuł 8a, ustęp 4 ustawy o VAT) | Dostawa towarów oraz świadczenie usług (art. 8a ust. 4 ustawy) | Dostawa towarów oraz świadczenie usług, których dotyczy bon jednego przeznaczenia na rzecz podatnika, który wyemitował bon zgodnie z art. 8a, ustęp 4 ustawy o VAT | Dostawa towarów oraz świadczenie usług, których dotyczy bon jednego przeznaczenia na rzecz podatnika, który wyemitował bon zgodnie z art. 8a ust. 4 ustawy |
| B_MPV_PROWIZJA | Usługi pośrednictwa dotyczące bonów różnego przeznaczenia | Usługi pośrednictwa dotyczące transferu bonu różnego przeznaczenia | Świadczenie usług pośrednictwa oraz innych usług dotyczących transferu bonu różnego przeznaczenia, opodatkowane zgodnie z art. 8b, ustęp 2 ustawy o VAT | Świadczenie usług pośrednictwa oraz innych usług dotyczących transferu bonu różnego przeznaczenia, opodatkowane zgodnie z art. 8b ust. 2 ustawy |
| WSTO_EE | Wewnątrzwspólnotowa sprzedaż towarów na odległość | Wewnątrzwspólnotowa sprzedaż towarów na odległość | Wewnątrzwspólnotowa sprzedaż towarów na odległość, które w momencie rozpoczynania wysyłki lub transportu, znajdują się na terytorium danego kraju, oraz świadczenie usług telekomunikacyjnych, emisyjnych i elektronicznych, o których mowa w art. 28k ustawy, osobom niepodlegającym opodatkowaniu, które są rezydentami lub mają stałe miejsce zamieszkania na terytorium kraju członkowskiego innego niż terytorium danego kraju. | Wewnątrzwspólnotowa sprzedaż towarów na odległość, które w momencie rozpoczynania wysyłki lub transportu, znajdują się na terytorium danego kraju, oraz świadczenie usług telekomunikacyjnych, emisyjnych i elektronicznych, o których mowa w art. 28k ustawy, osobom niepodlegającym opodatkowaniu, które są rezydentami lub mają stałe miejsce zamieszkania na terytorium kraju członkowskiego innego niż terytorium danego kraju |
| IED | Dostawa towarów, o których mowa w art. 7a, akapit 1 i 2 ustawy | Dostawa towarów, o której mowa w art. 7a ust. 1 i 2 ustawy | Dostawa towarów, których dotyczy artykuł 7a, akapity 1 i 2 ustawy, przez podatnika, który obsługuje dostawę, ale nie korzysta ze schematu specjalnego, o którym mowa w rozdziale 6a lub 9 sekcji XII ustawy lub w odpowiednich przepisach, w których miejsce dostawy znajduje się na terenie danego kraju. | Dostawa towarów, o której mowa w art. 7a ust. 1 i 2 ustawy, dokonanej przez podatnika ułatwiającego tę dostawę, który nie korzysta z procedury szczególnej, o której mowa w dziale XII w rozdziale 6a lub 9 ustawy lub w odpowiadających im regulacjach, dla której miejscem dostawy jest terytorium kraju |
| Inne           | Inne | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="goods-and-services-supplying-types-servicedeliveryselector"></a>Typy dostawy towarów i usług (ServiceDeliverySelector)

| Imię i nazwisko                    | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|-------------------------|------------|------------|------------------|------------------|
| ServiceDeliverySelector | Dostawy i świadczenia usług | Dostawy I świadczenia usług | Wskaźnik związany z dostawą i świadczeniem usług | Oznaczenie dotyczące dostawy i świadczenia usług |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Identyfikator konta odbiorcy
- Grupa odbiorców

To pole wyszukiwania definiuje warunki oparte na głównych źródłach danych bieżącej firmy. Warunki te dają w wyniku marker **1** dla odpowiadającego mu elementu z listy oznaczeń, które są związane z dostawami i świadczeniem usług (**GTU_\**_ znaczniki) pod tagiem _*\<SprzedazWiersz\>**. Można zaznaczyć więcej niż jedno oznaczenie dla tego samego rekordu należnego podatku VAT. Dlatego, jeśli firma musi zgłosić odmienne oznaczenia, muszą być dostępne odrębne warunki w danych głównych firmy.

Oznaczenia **GTU_\**_ nie są wymagane w przypadku dokumentów typu _* WEW** (wewnętrzny dokument) i **RO** (wewnętrzny dokument podsumowujący) (tag **\<TypDokumentu\>** pod tagiem **\<SprzedazWiersz\>**).

W poniższej tabeli przedstawiono wyniki wyszukiwania (oznaczenia) dla **ServiceDeliverySelector**.

| Imię i nazwisko     | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------|------------|------------|------------------|------------------|
| GTU_01   | Dostawa napojów alkoholowych | Dostawa napojów alkoholowych | Dostawa napojów alkoholowych o zawartości alkoholu powyżej 1,2%, piwa oraz napojów alkoholowych będących mieszaniną piwa i napojów bezalkoholowych, w których zawartość alkoholu przekracza 0,5% (CN od 2203 do 2208) | Dostawa napojów alkoholowych o zawartości alkoholu powyżej 1,2%, piwa oraz napojów alkoholowych będących mieszaniną piwa i napojów bezalkoholowych, w których zawartość alkoholu przekracza 0,5% (CN od 2203 do 2208) |
| GTU_02   | Dostawa towarów, o których mowa w art. 103, poz. 5aa | Dostawa towarów, o których mowa w art. 103 ust. 5aa | Dostawa towarów, o których mowa w art. 103, poz. 5aa ustawy o VAT | Dostawa towarów, o których mowa w art. 103 ust. 5aa ustawy |
| GTU_03   | Dostawa oleju opałowego | Dostawa oleju opałowego | Dostawa olejów opałowych nieujętych w GTU_02, olejów smarowych i pozostałych olejów (CN od 2710 19 71 do 2710 19 83 i CN od 2710 19 87 do 2710 19 99, z wyłączeniem smarów plastycznych zaliczonych do kodu CN 2710 19 99), olejów smarowych (CN 2710 20 90) oraz preparatów smarowych (CN 3403, z wyłączeniem smarów plastycznych objętych tą pozycją) | Dostawa olejów opałowych nieujętych w GTU_02, olejów i pozostałych olejów (CN od 2710 19 71 do 2710 19 83 I CN od 2710 19 87 do 2710 19 99, z wyłączeniem smarów zsych zsłownych do kodu CN 2710 19 99), olejów (CN 2710 20 90) i tejsówsów (CN 3403, z wyłączeniem smarów tej pozycją) |
| GTU_04   | Dostawa wyrobów tytoniowych | Dostawa wyrobów tytoniowych | Dostawa wyrobów tytoniowych, suszu tytoniowego, płynu do papierosów elektronicznych i wyrobów nowatorskich, w rozumieniu przepisów o podatku akcyzowym | Dostawa wyrobów tytoniowych, suszu tytoniowego, płynu do papierosów elektronicznych i wyrobów nowatorskich, w rozumieniu przepisów o podatku akcyzowym |
| GTU_05   | Dostawa odpadów | Dostawa odpadów | Dostawa odpadów - wyłącznie określonych w poz. od 79 do 91 załącznika 15 do ustawy o VAT | Dostawa odpadów - wyłącznie określonych w poz. 79-91 załącznika nr 15 do ustawy |
| GTU_06   | Dostawa urządzeń elektronicznych | Dostawa urządzeń elektronicznych | Dostawa urządzeń elektronicznych oraz części i materiałów do nich, o których mowa wyłącznie w pkt 7,8, 59 do 63, 65, 66, 69 i 94 do 96 załącznika nr 15 do ustawy o VAT oraz folii stretch określonej w poz. 9 niniejszego załącznika | Dostawa urządzeń elektronicznych oraz części i materiałów do nich, wyłącznie określonych w poz. 7, 8, 59-63, 65, 66, 69 i 94-96 załącznika nr 15 do ustawy, a także folii typu stretch określonej w poz. 9 tego załącznika |
| GTU_07   | Dostawa pojazdów | Dostawa pojazdów | Dostawa pojazdów oraz części o kodach wyłącznie od CN 8701 do 8708 | Dostawa pojazdów i części (CN od 8701 do 8708) |
| GTU_08   | Dostawa metali szlachetnych oraz nieszlachetnych | Dostawa metali szlachetnych oraz nieszlachetnych | Dostawa metali szlachetnych i nieszlachetnych, ale tylko tych wymienionych w pkt 1 załącznika nr 12 do ustawy o VAT oraz w pkt 12 do 25, 33 do 40, 45, 46, 56 i 78 załącznika 15 do ustawy o VAT. Ustawa o VAT | Dostawa metali szlachetnych oraz nieszlachetnych - wyłącznie określonych w poz. 1 załącznika nr 12 do ustawy oraz w poz. 12-25, 33-40, 45, 46, 56 i 78 załącznika nr 15 do ustawy |
| GTU_09   | Dostawa leków oraz wyrobów medycznych | Dostawa leków oraz wyrobów medycznych | Dostawa produktów leczniczych, środków spożywczych specjalnego przeznaczenia żywieniowego oraz wyrobów medycznych objętych wyłącznie obowiązkiem zgłoszenia, o którym mowa w art. 37av ust. 1 ustawy z dnia 6 września 2001 r. Prawo farmaceutyczne (Dz. z 2021 r. poz. 974 i 981 z późn. zm.) | Dostawa produktów leczniczych, środków spożywczych specjalnego przeznaczenia żywieniowego oraz wyrobów medycznych, wyłącznie objętych obowiązkiem zgłoszenia, o którym mowa w art. 37av ust. 1 ustawy z dnia 6 września 2001 r. - Prawo farmaceutyczne (Dz. U. z 2021 r. poz. 974 i 981, z późn. zm.) |
| GTU_10   | Dostawa budynków | Dostawa budynków | Dostawa budynków, budowli i gruntów oraz ich części i udziałów w prawie własności, w tym sprzedaż praw, o których mowa w art. 7 ust. 1 ustawy VAT  | Dostawa, budowle I gruntów i ich części I udziałów w prawie własności, w tym zbycia praw, o których mowa w art. 7 ust. 1 ustawy |
| GTU_11   | Świadczenie usług — gazy cieplarniane | Świadczenie usług — gazy cieplarniane | Świadczenie usług w zakresie przenoszenia uprawnień do emisji gazów cieplarnianych, o których mowa w ustawie z dnia 12 czerwca 2015 r. o systemie handlu uprawnieniami do emisji gazów cieplarnianych (Dz. U. z 2021 r. poz. 332 i 1047) | Świadczenie usług w zakresie przenoszenia uprawnień do emisji gazów cieplarnianych, o których mowa w ustawie z dnia 12 czerwca 2015 r. o systemie handlu uprawnieniami do emisji gazów cieplarnianych (Dz. U. z 2021 r. poz. 332 i 1047) |
| GTU_12   | Świadczenie usług o charakterze niematerialnym | Świadczenie usług o charakterze niematerialnym | Świadczenie usług o charakterze niematerialnym - wyłącznie: doradczych, w tym doradztwa prawnego i podatkowego oraz doradztwa związanego z zarządzaniem (PKWiU 62.02.1, 62.02.2, 66.19.91, 69.20.3, 70.22.11, 70.22.12, 70.22.13, 70.22.14, 70.22.15, 70.22.16, 70.22.3, 71.11.24, 71.11.42, 71.12.11, 71.12.31, 74.90.13, 74.90.15, 74.90.19), w zakresie rachunkowości i audytu finansowego (PKWiU 69.20.1, 69.20.2), prawnych (PKWiU 69.1), zarządczych (PKWiU 62.03, 63.11.12, 66.11.19, 66.30, 68.32, 69.20.4, 70.22.17, 70.22.2, 90.02.19.1), firm centralnych (PKWiU 70.1), marketingowych lub reklamowych (PKWiU 73.1), badania rynku i opinii publicznej (PKWiU 73.2), w zakresie badań naukowych i prac rozwojowych (PKWiU 72) oraz w zakresie pozaszkolnych form edukacji (PKWiU 85.5) | Świadczenie usług o charakterze niematerialnym - wyłącznie: doradczych, w tym doradztwa prawnego i podatkowego oraz doradztwa związanego z zarządzaniem (PKWiU 62.02.1, 62.02.2, 66.19.91, 69.20.3, 70.22.11, 70.22.12, 70.22.13, 70.22.14, 70.22.15, 70.22.16, 70.22.3, 71.11.24, 71.11.42, 71.12.11, 71.12.31, 74.90.13, 74.90.15, 74.90.19), w zakresie rachunkowości i audytu finansowego (PKWiU 69.20.1, 69.20.2), prawnych (PKWiU 69.1), zarządczych (PKWiU 62.03, 63.11.12, 66.11.19, 66.30, 68.32, 69.20.4, 70.22.17, 70.22.2, 90.02.19.1), firm centralnych (PKWiU 70.1), marketingowych lub reklamowych (PKWiU 73.1), badania rynku i opinii publicznej (PKWiU 73.2), w zakresie badań naukowych i prac rozwojowych (PKWiU 72) oraz w zakresie pozaszkolnych form edukacji (PKWiU 85.5) |
| GTU_13   | Świadczenie usług transportowych i gospodarki magazynowej | Świadczenie usług transportowych i gospodarki magazynowej | Świadczenie usług transportowych i gospodarka magazynowa, o których mowa w PKWiU 49.4, 52.1 | Świadczenie usług transportowych I gospodarki magazynowej — PKWiU 49.4, 52.1 |
| Inne     | Inna | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="declaration-markers-declarationmarkersselector"></a>Markery deklaracji (DeclarationMarkersSelector)

| Imię i nazwisko                       | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------------------------|------------|------------|------------------|------------------|
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

| Imię i nazwisko     | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------|------------|------------|------------------|------------------|
| P_65     | Czynności, o których mowa w art. 122 | Czynności o których mowa w art. 122 ustawy | Podatnik wykonywał w okresie rozliczeniowym czynności, o których mowa w art. 122 ustawy o VAT. Zwolnienie z podatku dostawy, importu i zakupu złota inwestycyjnego. | Podatnik wykonywał w okresie rozliczeniowym czynności, o których mowa w art. 122 ustawy |
| P_67     | Obniżenie kwoty zobowiązania podatkowego | Obniżenie kwoty zobowiązania podatkowego | Podatnik korzysta z obniżenia zobowiązania podatkowego, o którym mowa w art. 108d ustawy o VAT | Podatnik korzysta z obniżenia zobowiązania podatkowego, o którym mowa w art. 108d ustawy |
| Inne     | Inna | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="input-vat--margin-zakupvat_marzaselector"></a>Naliczony podatek VAT — marża (ZakupVAT_MarzaSelector)

| Imię i nazwisko                   | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|------------------------|------------|------------|------------------|------------------|
| ZakupVAT_MarzaSelector | Markery deklaracji | Podatek VAT — marża | Kwota zakupu towarów i usług od innych podatników na bezpośrednią korzyść turystów oraz ilość towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą, które są opodatkowane na podstawie marży, zgodnie z artykułem 120 ustawy o VAT | Kwota nabycia towarów i usług nabytych od innych podatników dla bezpośredniej korzyści turysty, a także nabycia towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą opodatkowaną na zasadzie marży zgodnie z art. 120 ustawy |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji

To pole wyszukiwania umożliwia zdefiniowanie różnych warunków poboru kwot, które muszą być zgłaszane w elemencie **ZakupWiersz/ZakupVAT_Marza** w raporcie. System zbiera kwoty brutto transakcji podatkowych spełniających określone kryteria. Jeśli warunki są zdefiniowane w jednym wierszu konfiguracji, system zastosuje je do źródłowej transakcji podatkowej za pomocą operatora **AND**. Jeśli warunki muszą być zastosowane za pomocą operatora **OR**, należy je zdefiniować w oddzielnych wierszach. W momencie, gdy transakcja podatkowa z okresu raportu spełnia warunek z listy, powiązana kwota brutto zostanie zebrana na potrzeby raportowania w elemencie **ZakupWiersz/ZakupVAT_Marza** raportu w odniesieniu do dokumentu.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **ZakupVAT_MarzaSelector**.

| Imię i nazwisko           | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------------|------------|------------|------------------|------------------|
| ZakupVAT_Marza | Naliczony podatek VAT — marża | Podatek VAT — marża | Kwota zakupu towarów i usług od innych podatników na bezpośrednią korzyść turystów oraz ilość towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą, które są opodatkowane na podstawie marży, zgodnie z artykułem 120 ustawy o VAT | Kwota nabycia towarów i usług nabytych od innych podatników dla bezpośredniej korzyści turysty, a także nabycia towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków związanych ze sprzedażą opodatkowaną na zasadzie marży zgodnie z art. 120 ustawy |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="document-types-for-sales-salesdocumenttypesselector"></a>Typy dokumentów dla sprzedaży (SalesDocumentTypesSelector)

| Imię i nazwisko                       | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------------------------|------------|------------|------------------|------------------|
| SalesDocumentTypesSelector | Typ dokumentu  | Typ dokumentu | Oznaczenie typu dokumentu sprzedaży | Oznaczenie dowodu sprzedaży |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Grupa podatków
- Identyfikator konta odbiorcy
- Grupa odbiorców

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **SalesDocumentTypesSelector**.

| Imię i nazwisko     | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------|------------|------------|------------------|------------------|
| FP       | Faktura, o której mowa w art. 109, ust. 3d | Faktura, o której mowa w art. 109 ust. 3d ustawy | Faktura, o której mowa w art. 109, ust. 3d ustawy o VAT | Faktura, o której mowa w art. 109 ust. 3d ustawy |
| RO       | Dokument zbiorczy wewnętrzny | Dokument zbiorczy wewnętrzny | Dokument zbiorczy wewnętrzny zawierający sprzedaż z kas rejestrujących | Dokument zbiorczy wewnętrzny zawierający sprzedaż z kas rejestrujących |
| WEW      | Dokument wewnętrzny | Dokument wewnętrzny | Dokument wewnętrzny | Dokument wewnętrzny |
| Inne     | Inna | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

Aby uzyskać więcej informacji dotyczących sposobu raportowania typów dokumentów **RO** i **FP** dla operacji handlu detalicznego, zapoznaj się z sekcją [Raportowanie typów dokumentów RO i FP dla operacji handlu detalicznego](emea-pol-vdek-scenarios.md#report-ro-and-fp-document-types-for-retail-operations) w dalszej części tego tematu.

### <a name="output-vat--margin-sprzedazvat_marzaselector"></a>Należny podatek VAT — marża (SprzedazVAT_MarzaSelector)

| Imię i nazwisko                      | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|---------------------------|------------|------------|------------------|------------------|
| SprzedazVAT_MarzaSelector | Należny podatek VAT — marża | VAT należny — marża | Wartość sprzedaży brutto dostaw towarów i usług, które są opodatkowane na podstawie marży, zgodnie z artykułami 119 i 120 ustawy o podatku VAT | Wartość sprzedaży brutto dostawy towarów i świadczenia usług opodatkowanych na zasadach marży zgodnie z art. 119 i art. 120 ustawy |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji

To pole wyszukiwania umożliwia definiowanie różnych warunków w celu raportowania markera **MR_T** lub **MR_UZ** dla dokumentów sprzedaży w elemencie **SprzedazWiersz** raportu.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **SprzedazVAT_MarzaSelector**.

| Imię i nazwisko     | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------|------------|------------|------------------|------------------|
| MR_T     | Usług turystyki opodatkowane na zasadach marży | Usług turystyki opodatkowane na zasadach marży | Świadczenie usług turystyki opodatkowane na zasadach marży zgodnie z art. 119 ustawy o VAT | Świadczenie usług turystyki opodatkowane na zasadach marży zgodnie z art. 119 ustawy |
| MR_UZ    | Dostawa towarów używanych, dzieł sztuki i antyków | Dostawa towarów używanych, dzieł sztuki i antyków | Dostawa towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków, opodatkowana na zasadach marży zgodnie z art. 120 ustawy o VAT | Dostawa towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków, opodatkowana na zasadach marży zgodnie z art. 120 ustawy |
| Inne     | Inna | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

### <a name="document-types-for-purchases-purchasedocumenttypesselector"></a>Typy dokumentów dla zakupów (PurchaseDocumentTypesSelector)

| Imię i nazwisko                          | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|-------------------------------|------------|------------|------------------|------------------|
| PurchaseDocumentTypesSelector | Typ faktury zakupu | Dokument zakupu | Oznaczenie typu dokumentu zakupu | Oznaczenie dowodu zakupu |

W przypadku tego pola wyszukiwania dostępne są następujące główne źródła danych do skonfigurowania:

- Kod podatku
- Grupa podatków dla pozycji
- Grupa podatków
- Identyfikator konta dostawcy
- Grupa dostawców

To pole wyszukiwania wyznacza kombinację kodu podatku (**Kod podatku**), identyfikatora konta dostawcy ID (**Identyfikator konta**) i grupy dostawców (**PartyGroup**) z bazy danych bieżącej firmy, z której będzie generowany typ dokumentu pod tagiem **\<ZakupWiersz\>**. Istnieje kilka kombinacji, które mogą być zdefiniowane.

W poniższej tabeli przedstawiono wyniki wyszukiwania dla **PurchaseDocumentTypesSelector**.

| Imię i nazwisko     | Etykieta (EN) | Etykieta (PL) | Opis (EN) | Opis (PL) |
|----------|------------|------------|------------------|------------------|
| MK       | Faktura, o której mowa w art. 21 | Faktura art. 21 | Faktura wystawiona przez podatnika będącego dostawcą lub usługodawcą, który wybrał metodę kasową rozliczeń określoną w art. 21 ustawy o VAT | Faktura wystawiona przez podatnika będącego dostawcą lub usługodawcą, który wybrał metodę kasową rozliczeń określoną w art. 21 ustawy |
| VAT_RR   | Faktura, o której mowa w art. 116 | Faktura VAT RR, art. 116 | Faktura VAT RR, o której mowa w art. 116 ustawy o VAT | Faktura VAT RR, o której mowa w art. 116 ustawy |
| WEW      | Dokument wewnętrzny | Dokument wewnętrzny | Dokument wewnętrzny | Dokument wewnętrzny |
| Inne     | Inna | | | |

> [!NOTE]
> Należy pamiętać, że należy dodać **Inne** (**Inne**), które muszą zbierać dane z innych przypadków jako ostatni element na liście. Wartość **Wiersz** musi być ostatnią wartością w tabeli. W kolumnie **Kod podatku** w wyniku wyszukiwania **Inne** wybierz **\*Niepuste\***.

## <a name="import-a-package-of-data-entities-that-includes-a-predefined-electronic-message-setup"></a><a id="import-data-entities-vdek"></a>Importowanie pakietu jednostek danych zawierającego wstępnie zdefiniowaną konfigurację wiadomości elektronicznych

Proces konfigurowania funkcji obsługi wiadomości elektronicznych do raportowania JPK-V7M ma wiele kroków. Ponieważ nazwy niektórych wstępnie zdefiniowanych jednostek są używane w konfiguracjach ER, ważne jest, aby użyć zbioru wstępnie zdefiniowanych wartości, które są dostarczane w pakiecie jednostek danych dla powiązanych tabel.

1. W [LCS](https://lcs.dynamics.com/v2) w obszarze Biblioteka udostępnionych elementów wybierz typ zasobu **Pakiet danych**. Następnie znajdź plik **PL JPK_V7M EM setup.zip** na liście plików pakietu danych i pobierz go do komputera.
2. Gdy plik **PL JPK_V7M EM setup.zip** zostanie pobrany, otwórz moduł Finance, wybierz firmę, z której będzie generowany raport JPK-V7M, a następnie przejdź do **Obszary robocze** \> **Zarządzanie danymi**.

    Przed zaimportowaniem danych konfiguracyjnych z pakietu encji danych należy się upewnić, że encje danych w aplikacji są odświeżane i synchronizowane.

3. W obszarze roboczym **Zarządzanie danymi** przejdź do **Parametry struktury** \> **Ustawienia jednostki**, a następnie wybierz pozycję **Odśwież listę jednostek**. Poczekaj na potwierdzenie, że odświeżanie zostało zakończone. Aby uzyskać więcej informacji na temat odświeżania listy jednostek, zapoznaj się z tematem [odświeżanie listy jednostek](../../fin-ops-core/dev-itpro/data-entities/data-entities.md#entity-list-refresh).
4. Sprawdź, czy dane źródłowe i dane docelowe są prawidłowo zmapowane. Aby uzyskać więcej informacji, zobacz [Sprawdź, czy dane źródłowe i dane docelowe są prawidłowo zmapowane](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md#validate-that-the-source-data-and-target-data-are-mapped-correctly).
5. Zanim jednostki danych zostaną użyte po raz pierwszy do importowania danych z pakietu, należy zsynchronizować mapowanie danych źródłowych i danych docelowych. Na liście dla pakietu wybierz jednostkę danych, a następnie w okienku akcji wybierz opcję **Modyfikuj mapowanie celu**. Następnie, nad siatką dla pakietu, wybierz opcję **Generuj mapowanie**, aby utworzyć mapowanie od początku.
6. Zapisz mapowanie.
7. Powtórz kroki od 3 do 6 dla każdej jednostki danych w pakiecie.

Aby uzyskać więcej informacji o zarządzaniu danymi, zobacz [Zarządzanie danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Teraz musisz zaimportować dane z pliku **PL JPK_V7M EM setup.zip** do wybranej firmy.

1. W obszarze roboczym **Zarządzanie danymi** wybierz opcję **Import**, w polu **Format danych źródłowych** wybierz opcję **Pakiet** i utwórz nowy projekt importowania, naciskając przycisk **Nowy** w okienku akcji.
2. Na skróconej karcie **Wybierz jednostki** wybierz pozycję **Dodaj plik**.
3. Wybierz **Przekaż i dodaj**, wybierz plik **PL JPK_V7M EM setup**.**zip** na komputerze i przekaż go.
4. Kliknij przycisk **Zamknij**, gdy jednostki z pakietu zostaną wyszczególnione na liście w siatce.
5. Kliknij przycisk **Importuj** w okienku akcji, aby rozpocząć importowanie danych z jednostek danych.

    ![Strona ustawień EM PL JPK_V7M](media/import-data-entities.jpg)

Otrzymasz powiadomienie w obszarze **Komunikaty** lub możesz odświeżyć stronę, aby wyświetlić postęp importowania danych. Po zakończeniu procesu importowania na stronie **Podsumowanie wykonywania** zostaną wyświetlone wyniki.

![Strona podsumowania wykonywania](media/data-entities-imported.jpg)

> [!IMPORTANT]
> Niektóre rekordy z jednostek danych w pakiecie zawierają łącze do konfiguracji ER. Dlatego przed rozpoczęciem importu pakietu jednostek danych należy najpierw zaimportować konfiguracje ER do modułu Finance.

## <a name="set-up-general-ledger-parameters"></a><a id="general-ledger-parameters-vdek"></a>Konfigurowanie parametrów księgi głównej

Aby pracować z funkcją obsługi wiadomości elektronicznych, należy zdefiniować powiązane sekwencje numerów.

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Parametry księgi głównej**.
2. Na karcie **Sekwencje numerów** skonfiguruj dwie sekwencje numerów:

    - Komunikat
    - Element wiadomości

## <a name="save-the-executable-class-parameters-for-electronic-messaging"></a><a id="executable-class-parameters-vdek"></a>Zapisywanie parametrów klasy wykonywalnej dla wiadomości elektronicznych

Podczas przetwarzania JPK-V7M używana jest klasa wykonywalna **EMGenerateJPKVDEKReportController_PL** w celu zainicjowania zbierania danych dla dostawcy danych raportu i dalszego generowania raportu. Przed pierwszym użyciem tej klasy należy zapisać jej parametry.

1. Przejdź do **Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Ustawienia klasy wykonywalnej**.
2. Wybierz klasę wykonywalną **Wygenerowanie JPK_V7M** (która ma wywoływać **EMGenerateJPKVDEKReportController_PL**), a następnie, w okienku akcji, wybierz **Parametry**. W oknie dialogowym **Generuj polski raport JPK_VDEK** naciśnij **OK**.

W oknie dialogowym klasy wykonywalnej grupa parametrów **Oznaczenie sprzedaży właściwe dla sprzedaży detalicznej** jest używana w scenariuszach właściwych dla sprzedaży detalicznej. Aby uzyskać więcej informacji dotyczących sposobu raportowania typów dokumentów **RO** i **FP** dla operacji handlu detalicznego, zapoznaj się z sekcją [Raportowanie typów dokumentów RO i FP dla operacji handlu detalicznego](emea-pol-vdek-scenarios.md#report-ro-and-fp-document-types-for-retail-operations) w dalszej części tego tematu. **Grupa parametrów znakowania** sprzedaży specyficzna dla sieci sprzedaży jest dostępna tylko w firmach, które mają podstawowy adres w Polsce.

Okno dialogowe dla klasy wykonywalnej zawiera parametr **Uwzględnij kody daty raportu VAT**. Ten parametr służy do zbierania transakcji VAT w raporcie na podstawie reguł, które definiujesz w kodach daty raportu VAT. Ten parametr nie ma wpływu na transakcje specyficzne dla sieci sprzedaży, które będą zgłaszane jako typ dokumentu **FP**. Aby uzyskać więcej informacji o funkcji kodów daty raportu VAT, zobacz temat [Ustawianie kodów daty raportu VAT](/dynamicsax-2012/appuser-itpro/pol-set-up-vat-report-date-codes). Parametr **Rozważ kody dat raportu podatku VAT** jest dostępny tylko w firmach, których adres podstawowy znajduje się w Polsce.

Okno dialogowe dla klasy wykonywalnej zawiera parametr **Okres rozliczeniowy**. Użyj tego parametru z funkcją [**Wiele numerów rejestracyjnych VAT**](emea-multiple-vat-registration-numbers.md) do zbierania transakcji VAT w określonych okresach rozliczenia podatku od sprzedaży. Parametr **Okres rozliczenia** jest dostępny w wersji finanse 10.0.29.

KB5007691 („Polska: Jednolity Plik Kontrolny VDEK (JPK-V7M, VDEK), zmiany ze stycznia 2022 w aplikacji Dynamics 365 Finance”) wprowadza parametr **Wersja schematu**. Ten parametr umożliwia określenie, że dodatkowe pole zawiera wersję schematu JPK-V7M, która ma zostać zgłoszona. Wybierz opcję **Wersja schematu** jako wartość tego pola.

Okno dialogowe dla klasy wykonywalnej zawiera parametr **Raportuj w walucie rozliczeniowej**. Domyślnie kwoty w raporcie są reprezentowane w walucie kodu podatku. Użyj tego parametru, aby raportować kwoty w JPK-V7M w walucie rozliczeniowej. Parametr **Raport w walucie rozliczeniowej** jest dostępny w wersji finansów 10.0.29.

## <a name="set-up-security-roles-for-electronic-message-processing"></a><a id="security-roles-vdek"></a>Konfigurowanie ról zabezpieczeń na potrzeby przetwarzania wiadomości elektronicznych

Różne grupy użytkowników mogą wymagać dostępu do przetwarzania JPK-V7M. Można ograniczyć dostęp do przetwarzania na podstawie grup zabezpieczeń zdefiniowanych w systemie.

Aby ograniczyć dostęp do przetwarzania JPK-V7M, należy wykonać następujące kroki.

1. Przejdź do menu **Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Przetwarzanie wiadomości elektronicznych**.
2. Wybierz przetwarzanie **JPK-V7M** i dodaj grupy zabezpieczeń, które muszą na nim pracować, na skróconej karcie **Role zabezpieczeń**. Jeśli dla przetwarzania nie zdefiniowano grupy zabezpieczeń, tylko administrator systemu może go zobaczyć na stronie **Wiadomości elektroniczne**.

## <a name="set-up-an-office-code-for-electronic-message-processing"></a><a id="office-code-vdek"></a>Konfigurowanie kodu urzędu na potrzeby przetwarzania wiadomości elektronicznych

Aby wprowadzić kod urzędu w dodatkowym polu **KodUrzedu**, należy wykonać poniższe kroki.

1. Przejdź do menu **Podatek** > **Ustawienia** > **Wiadomości elektroniczne** > **Przetwarzanie wiadomości elektronicznych**.
2. Wybierz przetwarzanie **JPK-V7M**.
3. Na skróconej karcie **Dodatkowe pole** wybierz dodatkowe pole **KodUrzedu**, a następnie, w polu **Wartość domyślna** określ kod urzędu, który ma być raportowany w elemencie **\<KodUrzedu\>** raportu.

## <a name="set-up-sales-tax-codes-and-sales-tax-reporting-codes"></a><a id="sales-tax-reporting-codes-vdek"></a>Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej

[Kod raportowania podatku](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md) jest wartością całkowitą. Kody raportowania podatku powinny być numerowane zgodnie z regułami obowiązującymi w firmie. Jednak zalecamy, aby różnicować kody według kierunku podatku. Użyj na przykład kodu pięciocyfrowego. Dla wszystkich transakcji wychodzących, które powinny być wykazywane w pierwszej części systemu podatku VAT, ustaw kody tak, aby były mniejsze lub równe 19999. Dla wszystkich transakcji przychodzących, które powinny być wykazywane w drugiej części systemu podatku VAT, ustaw kody tak, aby były większe lub równe 20000. W ten sposób uprościsz konfigurację raportów i eksportu danych, która opiera się na transakcjach podatkowych agregowanych według kodów raportowania podatku. Następujący przykład pokazuje użycie kodów sprawozdawczości podatkowej do generowania rejestru SAF sprzedaży i zakupów objętych podatkiem VAT. W tym przykładzie kody raportowania podatku są w formacie *ABBCC*. Ten format składa się z następujących elementów:

- **A** – Kierunek transakcji. Wartość wynosi **1** dla transakcji wychodzących, **2** dla transakcji przychodzących i **3** dla korekt.
- **BB** – Kod podatku. Numeracja zachowuje kolejność wśród wszystkich kodów podatków.
- **CC** – Numer typu transakcji w kodzie podatku. Parz tabela poniżej.

    | Typ transakcji                  | Numer typu transakcji     |
    |-----------------------------------|-----------------------------|
    | Sprzedaż opodatkowana                     | 01                          |
    | Sprzedaż wolna od podatku                    | 02                          |
    | Podatek należny                 | 03                          |
    | Opodatkowana faktura korygująca sprzedaży         | 04                          |
    | Faktura korygująca sprzedaży zwolnionej z podatku      | 05                          |
    | Podatek od faktury korygującej sprzedaży    | 6                          |
    | Zakup podlegający opodatkowaniu                 | 07                          |
    | Zakup wolny od podatku                 | 08                          |
    | Podatek naliczony              | 09                          |
    | Import opodatkowany                    | 10                          |
    | Przeciwstawna wartość importu podlegająca opodatkowaniu             | 11                          |
    | Podatek nienaliczony                           | 12                          |
    | Konto przeciwstawne podatku nienaliczonego                    | 13                          |
    | Opodatkowana faktura korygująca zakupu      | 14                          |
    | Faktura korygująca zakupu zwolnionego z podatku   | 15                          |
    | Podatek od faktury korygującej zakupu | 16                          |
    | Opodatkowana faktura korygująca importu        | 17                          |
    | Faktura korygująca przeciwstawnej wartości importu podlegającej opodatkowaniu | 18                          |

W poniższej tabeli przedstawiono kody podatków i kody sprawozdawczości podatkowej dla tego przykładu.

<table>
<thead>
<tr>
<th>Kod podatku</th>
<th>Kod raportowania podatku</th>
<th>Opis</th>
<th>Nazwa znacznika w JPK-V7M</th>
<th>Logowanie w JPK-V7M</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="4">ExportCust</td>
<td>10101</td>
<td>Sprzedaż opodatkowana</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td>10102</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td>10104</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td>10105</td>
<td>Faktura korygująca sprzedaży zwolnionej z podatku</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td rowspan="2">Art100_1.4</td>
<td>10201</td>
<td>Sprzedaż opodatkowana</td>
<td>K_11, K_12</td>
<td>-</td>
</tr>
<tr>
<td>10204</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_11, K_12</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5">VAT22_23</td>
<td>10301</td>
<td>Sprzedaż opodatkowana</td>
<td>K_19</td>
<td>-</td>
</tr>
<tr>
<td>10302</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10303</td>
<td>Podatek należny</td>
<td>K_20</td>
<td>-</td>
</tr>
<tr>
<td>10304</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_19</td>
<td>-</td>
</tr>
<tr>
<td>10306</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_20</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5">VAT7_8</td>
<td>10401</td>
<td>Sprzedaż opodatkowana</td>
<td>K_17</td>
<td>-</td>
</tr>
<tr>
<td>10402</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10403</td>
<td>Podatek należny</td>
<td>K_18</td>
<td>-</td>
</tr>
<tr>
<td>10404</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_17</td>
<td>-</td>
</tr>
<tr>
<td>10406</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_18</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5">VAT5</td>
<td>10501</td>
<td>Sprzedaż opodatkowana</td>
<td>K_15</td>
<td>-</td>
</tr>
<tr>
<td>10502</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10503</td>
<td>Podatek należny</td>
<td>K_16</td>
<td>-</td>
</tr>
<tr>
<td>10504</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_15</td>
<td>-</td>
</tr>
<tr>
<td>10506</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_16</td>
<td>-</td>
</tr>
<tr>
<td rowspan="3">VAT0</td>
<td>10601</td>
<td>Sprzedaż opodatkowana</td>
<td>K_13</td>
<td>-</td>
</tr>
<tr>
<td>10602</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10604</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_13</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4">ART129</td>
<td>10701</td>
<td>Sprzedaż opodatkowana</td>
<td>K_13, K_14</td>
<td>-</td>
</tr>
<tr>
<td>10702</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_13, K_14</td>
<td>-</td>
</tr>
<tr>
<td>10704</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_13, K_14</td>
<td>-</td>
</tr>
<tr>
<td>10705</td>
<td>Faktura korygująca sprzedaży zwolnionej z podatku</td>
<td>K_13, K_14</td>
<td>-</td>
</tr>
<tr>
<tr>
<td rowspan="4">VAT17_1.5</td>
<td>11901</td>
<td>Sprzedaż opodatkowana</td>
<td>K_31</td>
<td>-</td>
</tr>
<tr>
<td>11903</td>
<td>Podatek należny</td>
<td>K_32</td>
<td>-</td>
</tr>
<tr>
<td>11904</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_31</td>
<td>-</td>
</tr>
<tr>
<td>11906</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_32</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4">IntraEUGoods</td>
<td>10801</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_21</td>
<td>-</td>
</tr>
<tr>
<td>10810</td>
<td>Import opodatkowany</td>
<td>K_23</td>
<td>+</td>
</tr>
<tr>
<td>10811</td>
<td>Sprzedaż opodatkowana (opłata zwrotna)</td>
<td>K_23</td>
<td>-</td>
</tr>
<tr>
<td>10812</td>
<td>Podatek nienaliczony</td>
<td>K_24</td>
<td>+</td>
</tr>
<tr>
<td rowspan="2">ExportOfGoods</td>
<td>10901</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_22</td>
<td>-</td>
</tr>
<tr>
<td>10905</td>
<td>Faktura korygująca sprzedaży zwolnionej z podatku</td>
<td>K_22</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4">ImportOfGoodsART33</td>
<td>20207</td>
<td>Import opodatkowany</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>11010</td>
<td>Przeciwstawna wartość importu podlegająca opodatkowaniu</td>
<td>K_25</td>
<td>-</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek nienaliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>11012</td>
<td>Konto przeciwstawne podatku nienaliczonego</td>
<td>K_26</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5">ImportOfServices</td>
<td>20207</td>
<td>Import opodatkowany</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>11110</td>
<td>Przeciwstawna wartość importu podlegająca opodatkowaniu</td>
<td>K_27</td>
<td>-</td>
</tr>
<tr>
<td>11117</td>
<td>Sprzedaż opodatkowana (opłata zwrotna)</td>
<td>K_27</td>
<td>+</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek nienaliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>11112</td>
<td>Konto przeciwstawne podatku nienaliczonego</td>
<td>K_28</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5">ImportART28</td>
<td>20207</td>
<td>Import opodatkowany</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>11210</td>
<td>Przeciwstawna wartość importu podlegająca opodatkowaniu</td>
<td>K_29</td>
<td>-</td>
</tr>
<tr>
<td>11119</td>
<td>Sprzedaż opodatkowana (opłata zwrotna)</td>
<td>K_29</td>
<td>+</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek nienaliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>11212</td>
<td>Konto przeciwstawne podatku nienaliczonego</td>
<td>K_30</td>
<td>-</td>
</tr>
<td rowspan="4">FixedAssetPurch</td>
<td>20107</td>
<td>Zakup podlegający opodatkowaniu</td>
<td>K_40</td>
<td>+</td>
</tr>
<tr>
<td>20109</td>
<td>Podatek naliczony</td>
<td>K_41</td>
<td>+</td>
</tr>
<tr>
<td>20115</td>
<td>Opodatkowana faktura korygująca zakupu</td>
<td>K_40</td>
<td>+</td>
</tr>
<tr>
<td>20116</td>
<td>Podatek od faktury korygującej zakupu</td>
<td>K_44</td>
<td>+</td>
</tr>
<tr>
<td rowspan="4">GoodServPurch</td>
<td>20207</td>
<td>Zakup podlegający opodatkowaniu</td>
<td>K_42</td>
<td>+</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek naliczony</td>
<td>K_43</td>
<td>+</td>
</tr>
<tr>
<td>20215</td>
<td>Opodatkowana faktura korygująca zakupu</td>
<td>K_42</td>
<td>+</td>
</tr>
<tr>
<td>20216</td>
<td>Podatek od faktury korygującej zakupu</td>
<td>K_44</td>
<td>+</td>
</tr>
<tr>
<td rowspan="2">CorrATR89b1</td>
<td>30101</td>
<td>Podatek należny</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>30102</td>
<td>Podatek naliczony</td>
<td>K_47</td>
<td>+</td>
</tr>
<tr>
<td rowspan="2">CorrATR89b4</td>
<td>30201</td>
<td>Podatek należny</td>
<td>K_47</td>
<td>+</td>
</tr>
<tr>
<td>30202</td>
<td>Podatek naliczony</td>
<td>K_47</td>
<td>+</td>
</tr>
</tbody>
</table>

W przypadku faktur, które nie zostały opłacone w ciągu 150 dni, można zastosować zadanie okresowe [**Zaległa kwota podatku VAT stanowiąca zadłużenie**](emea-pol-sales-tax-reports.md#allowance-for-bad-debts). W takim przypadku można użyć tych samych kodów raportowania, które są używane dla K_41 i/lub K_43. System automatycznie interpretuje transakcje do raportowania w K_46 (Zaległa faktura) i K_47 (Opłacona zaległa faktura).
