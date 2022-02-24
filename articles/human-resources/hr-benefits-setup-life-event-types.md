---
title: Konfigurowanie typów zdarzeń zmiany sytuacji życiowej
description: Program Microsoft Dynamics 365 Human Resources używa typów zmiany sytuacji życiowej do zdefiniowania zdarzeń, które uzasadniają aktualizowanie rejestracji pracowników na świadczenia.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 5286bcd940f4068531bae624876c8a35e64db4c3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420054"
---
# <a name="configure-life-event-types"></a>Konfigurowanie typów zdarzeń zmiany sytuacji życiowej

Microsoft Dynamics 365 Human Resources używa typów zmiany sytuacji życiowej do zdefiniowania zdarzeń, które uzasadniają aktualizowanie rejestracji pracowników na świadczenia. Na przykład zawarcie związku małżeńskiego czy narodziny dziecka. Każdy identyfikator typu zmiany sytuacji życiowej może być skojarzony tylko z jednym typem zmiany sytuacji życiowej. Jeśli na przykład utworzysz identyfikator zmiany sytuacji życiowej o nazwie Zmiana adresu, który jest skojarzony z typem zmiany sytuacji życiowej Adres pracownika etatowego, nie można utworzyć kolejnego identyfikatora o nazwie Zmiana adresu pracownika etatowego i skojarzyć go z typem zmiany sytuacji życiowej Zmiana adresu pracownika etatowego. 

Po utworzeniu typów zmian sytuacji życiowej należy je skojarzyć z typami planów. Aby uzyskać więcej informacji, zobacz [Tworzenie typów planów](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > Podczas tworzenia zmiany sytuacji życiowej należy ją skojarzyć z typem planu. Aby uzyskać więcej informacji, zobacz [Tworzenie typów planów](hr-benefits-setup-life-event-types.md).

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
| **Zmiana stanu zatrudnienia** | <ul><li>Pracownik > Zatrudnienie</li><li>Strona Historia zatrudnienia</li></ul> | Zmiana stanu zatrudnienia |
| **Zmiana adresu pracownika etatowego** | <ul><li>Pracownik > Profil > Adresy </li><li>Pracownik > Dane osobowe > Kontakty osobiste > Adres</li></ul> Dodanie, edytowanie lub usunięcie adresu |
| **Zmiana osoby na utrzymaniu** | <ul><li>Pracownik > Profil > Dane osobowe > Kontakty osobiste > Dodaj lub usuń osobę na utrzymaniu</li><li>Samoobsługa pracownika etatowego</li></ul> | Dodanie lub usunięcie osoby na utrzymaniu. Kontakt osobisty musi być dzieckiem, współmałżonkiem, partnerem domowym lub byłym współmałżonkiem. Aktualizacja daty w polu **Początek ważności** powoduje zainicjowanie zmiany sytuacji życiowej. Jeśli data nie zostanie zaktualizowana, żadna sytuacji życiowej nie zostanie zainicjowana. |
| **Narodziny lub adopcja (osoba na utrzymaniu)** | <ul><li>Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu</li><li>Samoobsługa pracownika etatowego</li></ul> | Wypełnienie pola **Data adopcji**. Data urodzenia dziecka jest wymagana. |
| **Utrata objęcia świadczeniem (współmałżonek/partner domowy)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Utrata objęcia świadczeniem | Zaznaczenie opcji **Utrata objęcia świadczeniem** dla kontaktu osobistego oraz zaznaczenie opcji **Data wejścia w życie** |
| Zmiana zatrudnienia partnera krajowego | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Zatrudniono | <ul><li>Utworzenie rekordu szczegółów osoby na utrzymaniu i zaznaczenie wartości Tak w polu **Kontakt osobisty zatrudniony**</li><li>Zmiana wartości w polu **Kontakt osobisty zatrudniony** (Tak lub Nie)</li></ul> |
| **Nieobecność (współmałżonek/partner krajowy)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Nieobecność | <ul><li>Utworzenie rekordu szczegółów osoby na utrzymaniu oraz wypełnienie pola **EhrLOAEffectiveDate**</li><li>Zmiana wartości w polu **personPrivateDetails.EhrIsLOA** (Tak lub Nie)</li><li>Zmiana wartości w polu **personPrivateDetails.EhrLOAEffectiveDate**</li></ul> |
| **Zmiana w objęciu świadczeniem (stanowisko)** | <ul><li>Pracownik > Przypisanie stanowiska > Przypisania pracowników do stanowisk</li><li>Stanowiska > Stanowiska</li></ul> | <ul><li>Zmiana na stanowisko ustawione w rekordach przypisania pracowników do stanowisk</li><li>Zmiana przypisania pracownika do stanowiska</li></ul> |
| **Ubezpieczenie Medicare (pracownik etatowy/osoba na utrzymaniu)** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Data wejścia w życie ubezpieczenia Medicare | Zmiana nie jest inicjowana automatycznie po wprowadzeniu daty wejścia w życie przez kontakt osobisty. |
| **Pomoc nakazana przez sąd** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Osoba na utrzymaniu > Pomoc nakazana przez sąd (QMSCO/QDRO) i daty wejścia w życie | Nie powoduje zainicjowania żadnych automatycznych aktualizacji. Nie wpływa na uprawnienia; rejestruje zmianę sytuacji życiowej. |
| **Zgon** | Pracownik > Profil > Dane osobowe > Data zgonu | Wprowadzenie daty zgonu |
| **Dowody ubezpieczenia** | <ul><li>Pracownik > Pracownik > Wersje > Historia zatrudnienia > Menedżer dat > Szczegóły świadczenia</li><li> Pracownik > Zatrudnienie > Szczegóły świadczenia > Data weryfikacji</li></ul> | <ul><li>Wprowadzenie daty weryfikacji przez pracownika</li><li>Ustawienie wartości **Tak** w polu EvidenceOfInsurability przez pracownika</li></ul> |
| **Beneficjent** | Pracownik > Profil > Dane osobowe > Kontakty osobiste | Dodanie kontaktu osobistego oraz wypełnienie pól **Beneficjent** i **Data wejścia w życie**. Kontakt osobisty musi być typu **Dziecko**, **Współmałżonek**, **DomesticPartner**, **Rodzeństwo**, **FamilyContact**, **OtherContact**, **Rodzic**, **BeneficiaryEstate**, **BeneficiaryOrg** lub **BeneficiaryTrust**. |
| **Ubezpieczenie Medicare pracownika etatowego** | Pracownik > Pracownik > Wersje > Historia zatrudnienia > Menedżer dat > Szczegóły świadczenia | <ul><li>Zmiana wartości pola **EhrMedicareEligibilityDate**</li><li>Ustawienie wartości wartość **Tak** w polu **MedicareEligibile**</li></ul> |
| **Data urodzenia** | Pracownik > Profil > Dane osobowe > Kontakty osobiste > Szczegóły osoby na utrzymaniu > Data urodzenia | Dodanie lub zaktualizowanie daty urodzenia (nie po zakończeniu przetwarzania zmiany sytuacji życiowej). Przykład: jeśli w obszarze **Opcje uprawnień kontaktów osobistych** dla dziecka zostanie ustawiona opcja Wiek: 26 (Konfiguracja > Świadczenia > Opcje uprawnień kontaktów osobistych), a pracownicy działu kadr wykonają przetwarzanie zmiany sytuacji życiowej jeden dzień po ukończeniu 26. roku życia przez osobę na utrzymaniu, zostanie wyświetlony komunikat informujący o tym, że osoba na utrzymaniu nie będzie już dłużej się kwalifikować do objęcia świadczeniami. |
| **Zmiana uprawnień pracownika (niewyłączna dla Stanów Zjednoczonych)** | <ul><li>Pracownik > Zatrudnienie</li><li>Pracownik > Pracownik > Wersje > Historia zatrudnienia</li></ul> | <ul><li>Zmiana typu pracownika, kategorii zatrudnienia lub wartości w jednym z pięciu pól uprawnień definiowanych przez użytkownika</li><li>Zmiana wartości pola **HcmEmploymentDetail.EhrEmploymentType** (przetwarzane tylko dla *zmodyfikowanych* rekordów szczegółów zatrudnienia, nieprzetwarzane dla *nowych* rekordów zatrudnienia, np. ponownego zatrudnienia czy zakończenia zatrudnienia)</li></ul> |
| **Nowe zastąpienie uprawnień (niewyłączne dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Świadczenia > Zastąpienie reguły uprawnienia | Wykonanie przetwarzania zmiany sytuacji życiowej | EhrBenefitEligibilityRuleOverride.ValidFrom |
| **Zmiana zastąpienia reguły uprawnienia (niewyłączna dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Świadczenia > Zastąpienie reguły uprawnienia | Wykonanie przetwarzania zmiany sytuacji życiowej (uwzględnia tylko zmiany wartości pól **ValidFrom** i **ValidTo** w ustawieniu Zastąpienie reguły uprawnienia) |
| **Zmiana wygaśnięcia zastąpienia reguły uprawnienia (niewyłączna dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Świadczenia > Zastąpienie reguły uprawnienia | Wykonanie przetwarzania zmiany sytuacji życiowej. Jeśli na przykład zmodyfikujesz datę ważności zastąpienia reguły uprawnienia w planie na dzisiaj o 17:00, dowolną godzinę po 17:00 lub dowolny z następnych dni, po czym wykonasz przetwarzanie zmiany sytuacji życiowej, pojawi się komunikat informujący o wygaśnięciu zastąpienia reguły uprawnienia. |
| **Nowy plan świadczeń (niewyłączny dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Plany > Nowy | <ul><li>Dodanie opcji uprawnień do bieżącego planu</li><li>Dodanie nowego planu z dołączonymi opcjami uprawnień</li></ul></br></br>Pracownicy działu kadr powinni wykonać przetwarzanie uprawnień do świadczeń z powodu zmiany sytuacji życiowej. |
| **Zmiana reguły uprawnienia (niewyłączna dla Stanów Zjednoczonych)** | Zasoby ludzkie — zaawansowane > Świadczenia > Reguły/opcje > Reguły uprawnienia | Wykonanie przetwarzania uprawnień do świadczeń z powodu zmiany sytuacji życiowej. Rejestrowane, gdy w rekordach encji **EhrBenefitEligibilityRule** zmieni się następująca wartość: **UseEmplCategory**, **UseEmplStatus** lub **UseEmplType**. Powoduje aktualizację tylko tych transakcji zmiany sytuacji życiowej, które już istnieją dla zmienionej reguły lub kryteriów uprawnień. |
