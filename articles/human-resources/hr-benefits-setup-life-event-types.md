---
title: Konfigurowanie typów zdarzeń zmiany sytuacji życiowej
description: Program Microsoft Dynamics 365 Human Resources używa typów zmiany sytuacji życiowej do zdefiniowania zdarzeń, które uzasadniają aktualizowanie rejestracji pracowników na świadczenia.
author: andreabichsel
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f04be1c0852970db337766757ff6f412bbf5c38
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921124"
---
# <a name="configure-life-event-types"></a>Konfigurowanie typów zdarzeń zmiany sytuacji życiowej

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources używa typów zmiany sytuacji życiowej do zdefiniowania zdarzeń, które uzasadniają aktualizowanie rejestracji pracowników na świadczenia, jak na przykład zawarcie związku małżeńskiego czy narodziny dziecka. Każdy identyfikator typu zmiany sytuacji życiowej może być skojarzony tylko z jednym typem zmiany sytuacji życiowej. Jeśli na przykład utworzysz identyfikator zmiany sytuacji życiowej o nazwie Zmiana adresu, który jest skojarzony z typem zmiany sytuacji życiowej Adres pracownika etatowego, nie można utworzyć kolejnego identyfikatora o nazwie Zmiana adresu pracownika etatowego i skojarzyć go z typem zmiany sytuacji życiowej Zmiana adresu pracownika etatowego. Jeśli typ zdarzenia zmiany sytuacji życiowej nie jest skojarzony z typem planu, typ zdarzenia zmiany sytuacji życiowej nie wywoła zmiany sytuacji życiowej. Aby uzyskać więcej informacji, zobacz [Tworzenie typów planów](hr-benefits-setup-plan-types.md).

## <a name="create-a-life-event-type"></a>Tworzenie typu zmiany sytuacji życiowej

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Typy zmian sytuacji życiowej**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Identyfikator typu zdarzenia zmiany sytuacji życiowej** | Unikatowy identyfikator typu zmiany sytuacji życiowej. |
   | **Opis** | Opis typu zmiany sytuacji życiowej. |
   | **Typ zdarzenia zmiany sytuacji życiowej** | Katalizator aktualizujący rejestrację pracownika na świadczenia. Aby wyświetlić listę zmian sytuacji życiowej, zobacz poniżej punkt [Zmiany sytuacji życiowej](hr-benefits-setup-payment-frequencies.md?life-events). |

4. Wybierz opcję **Zapisz**.

## <a name="view-attached-plans"></a>Wyświetlanie dołączonych planów

Istnieje możliwość wyświetlenia listy planów dołączonych do wybranego typu zmiany sytuacji życiowej. Zmiany sytuacji życiowej są dołączone do typu planu, a typy planów są skojarzone z planem.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Typy zmian sytuacji życiowej**.

2. Wybierz opcję **Akcje**.

3. Wybierz opcję **Dołączone plany**.

## <a name="life-events"></a>Zdarzenia zmiany sytuacji życiowej

Podczas tworzenia typu zmiany sytuacji życiowej można wybierać spośród następujących zmian sytuacji życiowej:

| Zdarzenie zmiany sytuacji życiowej | Lokalizacja | Wyzwalacz |
| --- | --- | --- |
| **Zmiana stanu cywilnego** | Pracownik > Profil > Dane osobowe > Stan cywilny| Zmiana stanu cywilnego |
| **Zmiana stanu zatrudnienia** | Pracownik > Zatrudnienie<br>Strona Historia zatrudnienia | W przypadku pracownika z istniejącymi szczegółami zatrudnienia tworzenie nowych szczegółów zatrudnienia o innym stanie zatrudnienia wyzwala zdarzenie zmiany sytuacji życiowej.  Aktualizacja istniejących szczegółów zatrudnienia z innym stanem zatrudnienia wywoła również zdarzenie zmiany sytuacji życiowej.  |
| **Zmiana adresu pracownika etatowego** | Pracownik > Profil > Adresy<br>Pracownik > Dane osobowe > Kontakty osobiste > Adres | Zmiana w adresie. Adres musi być adresem podstawowym do wyzwalania zdarzenia zmiany sytuacji życiowej. |
| **Zmiana osoby na utrzymaniu** | Pracownik > Profil > Dane osobowe > Kontakty osobiste<br>Samoobsługa pracownika etatowego | Dodaj kontakt osobisty, określając go jako zależny i wskazując wartość w polu **Ważny od**. Zaktualizuj informacje **Ważny do** zależnego kontaktu osobistego. Kontakt osobisty musi być dzieckiem, współmałżonkiem, partnerem domowym lub byłym współmałżonkiem.  |
| **Narodziny lub adopcja (osoba na utrzymaniu)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste<br>Samoobsługa pracownika > Edytuj dane osobowe > Kontakty osobiste | **Data urodzenia** lub **data adopcji** są dodawane lub aktualizowane. **Data urodzenia** dziecka jest wymagana. |
| **Utrata objęcia świadczeniem (współmałżonek/partner domowy)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Utrata objęcia świadczeniem | Zaznaczenie opcji **Utrata objęcia świadczeniem** dla kontaktu osobistego oraz zaznaczenie opcji **Data wejścia w życie** |
| Zmiana zatrudnienia partnera krajowego | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Zatrudniono | Tworzenie kontaktu osobistego i ustawienie opcji **Zatrudniony** na **tak**. Aktualizowanie kontaktu osobistego i zmiana ustawienia **Zatrudniony**.  |
| **Nieobecność (współmałżonek/partner krajowy)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Nieobecność | Utworzono kontakt osobisty oraz zdefiniowano wartość **Data rozpoczęcia nieobecności**. Zaktualizowano wartość **Nieobecność** kontaktu osobistego. Zaktualizowano wartość **Data rozpoczęcia nieobecności** kontaktu osobistego.  |
| **Zmiana w objęciu świadczeniem (stanowisko)** | Pracownik > Przypisanie stanowiska > Przypisania pracowników do stanowisk<br>Stanowiska > Stanowiska | Zmiana na stanowisko ustawione w rekordach przypisania pracowników do stanowisk. Zmiana przypisania pracownika do stanowiska. |
| **Zmiana w objęciu świadczeniem (wynagrodzenie)** | Pracownik > Wynagrodzenie > Plan stałych wynagrodzeń<br>Pracownik > Informacje osobiste > Roczne wynagrodzenie z tytułu świadczenia | Jeśli opcja Zarządzanie świadczeniami > Wspólne parametry zasobów ludzkich > Świadczenia > Roczne wynagrodzenie z tytułu świadczenia nie jest włączona, aktualizacja wartości Pracownik > Wynagrodzenie > Plan stałych wynagrodzeń spowoduje utworzenie zdarzenia zmiany sytuacji życiowej. Jeśli opcja Zarządzanie świadczeniami > Wspólne parametry zasobów ludzkich > Świadczenia > Roczne wynagrodzenie z tytułu świadczenia jest włączona, aktualizacja wartości Pracownik > Informacje osobiste > Roczne wynagrodzenie z tytułu świadczenia spowoduje utworzenie zdarzenia zmiany sytuacji życiowej. |
| **Ubezpieczenie Medicare (pracownik etatowy/osoba na utrzymaniu)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Data wejścia w życie ubezpieczenia Medicare | Dodanie lub aktualizacja daty **Rozpoczęcie ważności programu Medicare** dla kontaktu osobistego powoduje utworzenie tego zdarzenia zmiany sytuacji życiowej. |
| **Pomoc nakazana przez sąd** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Osoba na utrzymaniu > Pomoc nakazana przez sąd (QMSCO/QDRO) i daty wejścia w życie | Podczas tworzenia kontaktu osobistego zostanie utworzone zdarzenie zmiany sytuacji życiowej, jeśli w polu **Alimenty orzeczone sądownie** jest wybrana wartość **Tak**. Aktualizacja wartości w polu **Alimenty orzeczone sądownie** lub **Data ważności orzeczenia sądu** również wywoła zdarzenie zmiany sytuacji życiowej. |
| **Zgon** | Pracownik > Profil > Dane osobowe > Data zgonu | Wprowadzenie lub aktualizacja daty zgonu. |
| **Dowody ubezpieczenia** | Pracownik > Pracownik > Wersje > Historia zatrudnienia > Menedżer dat > Szczegóły świadczenia | W polu **Dowody dotyczące ubezpieczenia** jest ustawiona wartość **Tak**. Wartość w polu **Data weryfikacji dowodu dotyczącego ubezpieczenia** jest określona. |
| **Beneficjent** | Pracownik > Profil > Dane osobowe > Kontakty osobiste | Dodanie kontaktu osobistego oraz wypełnienie pól **Beneficjent** i **Data wejścia w życie**. Kontakt osobisty musi być typu **Dziecko**, **Współmałżonek**, **DomesticPartner**, **Rodzeństwo**, **FamilyContact**, **OtherContact** lub **Rodzic**. |
| **Ubezpieczenie Medicare pracownika etatowego** | Pracownik > Pracownik > Wersje > Historia zatrudnienia > Menedżer dat > Szczegóły świadczenia | Ustawienie wartości wartość **Tak** w polu **Przysługuje Medicare**. Zmiana wartości pola **Data przysługiwania Medicare**. |
| **Data urodzenia** | Zarządzanie świadczeniami > Przetwarzanie zdarzeń zmiany sytuacji życiowej | Te zdarzenia zmiany sytuacji życiowej są tworzone z **przetwarzania zdarzeń zmiany sytuacji życiowej**. Proces analizuje wybrany okres i osobę prawną i znajduje skojarzonych z nim pracowników. Oblicza ostatnie urodziny i tworzy zdarzenie zmiany sytuacji życiowej urodzin, jeśli jeszcze nie zostało utworzone. |
| **Zmiana uprawnień pracownika (niewyłączna dla Stanów Zjednoczonych)** | Pracownik > Zatrudnienie<br>Pracownik > Pracownik > Wersje > Historia zatrudnienia | Tworzy zdarzenie zmiany sytuacji życiowej, gdy:<br><ul><li>Jest tworzone nowe zatrudnienie, a istnieje poprzednie zatrudnienie i typ pracownika zmienia się.</li><li>Są tworzone szczegóły nowego zatrudnienia, a istnieją szczegóły poprzedniego zatrudnienia i typ zatrudnienia lub kategoria zatrudnienia zmienia się.</li><li>Jest aktualizowany rekord zatrudnienia i zdefiniowano inny typ pracownika.</li><li>Jest aktualizowany rekord szczegółów zatrudnienia i określono inny typ lub kategorię zatrudnienia.</li></ul> |
| **Nowe zastąpienie uprawnień (niewyłączne dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Świadczenia > Zastąpienie reguły uprawnienia | Wykonanie przetwarzania zmiany sytuacji życiowej<br>Utworzenie nowego zastąpienia uprawnień do planu świadczeń dla pracownika wyzwala to zdarzenie zmiany sytuacji życiowej.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Zmiana zastąpienia reguły uprawnienia (niewyłączna dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Świadczenia > Zastąpienie reguły uprawnienia | Aktualizacja wartości **Obowiązuje od** lub **Obowiązuje do** w zastępowaniu uprawnień do planu świadczeń wyzwala to zdarzenie zmiany sytuacji życiowej. |
| **Zmiana wygaśnięcia zastąpienia reguły uprawnienia (niewyłączna dla Stanów Zjednoczonych)** | Zarządzanie świadczeniami > Przetwarzanie zdarzeń zmiany sytuacji życiowej  | Te zdarzenia zmiany sytuacji życiowej są tworzone z **przetwarzania zdarzeń zmiany sytuacji życiowej**. Proces analizuje wybrany okres i osobę prawną i znajduje skojarzone z nim zastąpienia uprawnień do planu świadczeń. Tworzy zdarzenia zmiany sytuacji życiowej, jeśli zastąpienia wygasły. |
| **Nowy plan świadczeń (niewyłączny dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Nowy | Opcje uprawnień są dodane do bieżącego planu. Nowy plan z dołączonymi opcjami uprawnień jest dodany.</br></br>Pracownicy działu kadr powinni wykonać przetwarzanie uprawnień do świadczeń z powodu zmiany sytuacji życiowej. |
| **Zmiana reguły uprawnienia (niewyłączna dla Stanów Zjednoczonych)** | Zarządzanie świadczeniami > Reguły uprawnienia | Wykonanie przetwarzania uprawnień do świadczeń z powodu zmiany sytuacji życiowej. Rejestrowane, gdy w rekordach encji **BenefitEligibilityRule** zmieni się następująca wartość: **UseEmplCategory**, **UseEmplStatus** lub **UseEmplType**. Powoduje aktualizację tylko tych transakcji zmiany sytuacji życiowej, które już istnieją dla zmienionej reguły lub kryteriów uprawnień. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]