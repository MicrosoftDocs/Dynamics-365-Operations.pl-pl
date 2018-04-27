---
title: "Konfigurowanie zarządzania wydatkami"
description: "W tym artykule opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed skonfigurowaniem modułu Zarządzanie wydatkami w programie Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c87909d9eb3a4d717e0c40289353da0267a51f60
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="configure-expense-management"></a>Konfigurowanie zarządzania wydatkami

[!INCLUDE [banner](../includes/banner.md)]

W tym temacie opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed skonfigurowaniem modułu Zarządzanie wydatkami w programie Microsoft Dynamics 365 for Finance and Operations. W funkcji Zarządzanie wydatkami można przechowywać informacje o metodach płatności, wnioski wyjazdowe, raporty z wydatków oraz zasady itp.

Ponieważ wiele decyzji podjętych podczas planowania konfiguracji zarządzania wydatkami jest opartych na hierarchii i strukturze finansowej organizacji, musisz konsultować się z dokumentami planowania dla tych dokumentów.

## <a name="intercompany-expenses"></a>Wydatki międzyfirmowe

Jeśli włączysz wydatki międzyfirmowe, zezwalasz firmom i pracownikom na tworzenie wydatków lub pobieranie opłat w imieniu lub od innych zatrudniających firm w obrębie organizacji. Przykładowo pracownik w firmie A kończy projekt dla firmy B, a projekt powoduje powstanie wydatków związanych z wyjazdem. Jeżeli wydatki międzyfirmowe są włączone, pracownik może przesłać raport o wydatkach, który spowoduje zaksięgowanie wydatku w firmie B, a wydatek musi zostać zwrócony przez firmę A. Jeśli Twoja organizacja nie ma wielu podmiotów prawnych, nie musisz włączać wydatków międzyfirmowych.

**Decyzja:** Czy chcesz włączyć wydatki międzyfirmowe?

## <a name="financial-management"></a>Zarządzanie finansami

Zarządzanie wydatkami jest ściśle zintegrowane z zarządzaniem finansami organizacji. Wiele konfiguracji zarządzania wydatkami będzie opierać się na decyzjach dotyczących finansów organizacji. W poniższych sekcjach opisano różne obszary, które wymagają planowania i decyzji opartych na decyzjach finansowych i wskazówkach organizacji pochodzących od zespołu kierowniczego.

### <a name="per-diems"></a>Diety

Musisz zdefiniować pracownika dla diet oferowanych przez organizację. Ponieważ diety są zazwyczaj używane w celu pokrycia wydatków, takich jak wyżywienie, zakwaterowanie i inne koszty dodatkowe, można utworzyć reguły dla odpisów diet oferowanych przez organizację. Stawki diet można określić na podstawie sezonu roku lub lokalizacji podróży albo ich obu. Podczas definiowania reguły obliczania diety można określić, że pewien procent stawki diety zostanie wstrzymany, jeśli pracownik otrzymuje bezpłatne posiłki lub usługi. Można także zdefiniować poziom stawek diet, aby wyznaczyć minimalną i maksymalną liczbę godzin, dla których można zastosować stawkę diety dla wyjazdu pracownika.

**Decyzje:**

- Domyślne reguły obliczania diet dla pierwszego i ostatniego dnia:

    - Jaka jest minimalna liczba godzin, co to której pracownik może zgłosić roszczenie z dzień, i mimo to otrzymać dietę?
    - Czy obowiązuje zmniejszenie kwoty, jaka jest oferowana za posiłki w pierwszym i ostatnim dniu? Czy istnieje redukcja, jaki jest procent redukcji?
    - Czy obowiązuje zmniejszenie kwoty, jaka jest oferowana za hotele w pierwszym i ostatnim dniu? Czy istnieje redukcja, jaki jest procent redukcji?
    - Czy obowiązuje zmniejszenie kwoty, jaka jest oferowana za inne wydatki poniesione w pierwszym i ostatnim dniu? Czy istnieje redukcja, jaki jest procent redukcji?

- Domyślne reguły obliczania diet:

    - Czy obowiązuje procentowe zmniejszenie przydziału diety za każdy posiłek, jeśli na przykład posiłek jest bezpłatny? Czy istnieje redukcja, jaki jest procent redukcji dla każdego posiłku?
    - Obniżka za posiłek jest obliczana za dzień, za wyjazd lub według liczby posiłków dziennie?
    - Czy kwoty diety powinny być zaokrąglane standardowo czy w górę?
    - Czy diety są obliczane według cykli 24-godzinnych czy według dni kalendarzowych?

- Reguły obliczania diet na podstawie lokalizacji:

    - Stawki diet różnią się w zależności od lokalizacji? Jakie lokalizacje są uwzględnione?
    - Jeżeli stawki diet różnią się w zależności od lokalizacji, jaka kwota procentowo jest dostępna dla następujących typów wydatków w każdej lokalizacji:

        - Posiłki
        - Hotel
        - Inne wydatki

### <a name="expense-management-journals-and-accounts"></a>Konta i arkusze zarządzania wydatkami

Zarządzanie wydatkami wymaga użycia wielu arkuszy i kont. Trzeba zdecydować, na przykład, czy to samo konto jest używane dla zaliczek gotówkowych i spory dotyczących kart kredytowych.

**Decyzje:**

- Do którego arkusza księgi księgowane są zatwierdzone raporty wydatków?
- Które konto jest używane dla zaliczek gotówkowych?
- Czy zaliczki gotówkowe powinny być księgowane natychmiast?

### <a name="payment-methods"></a>Metody płatności

Jeśli zezwalasz pracownikom na ponoszenie wydatków w imieniu Twojej firmy, musisz określić metody płatności, których pracownicy mogą używać. Na przykład możesz zezwolić pracownikom na używanie gotówki lub firmowej karty kredytowej. Możesz też zezwolić pracownikom na używanie osobistych kart kredytowych, a następnie zwracać im pieniądze. Należy podjąć następujące decyzje dla każdej dozwolonej metody płatności.

**Decyzje:**

- Jakie metody płatności są dozwolone?
- Kto jest właścicielem wydatków poniesionych przy użyciu metody płatności?
- Czy jest dostępny typ konta przeciwstawnego? Jeśli dostępne jest konto typu przeciwstawnego, co nim jest?
- Jeśli dostępne jest konto przeciwstawne, co nim jest?
- Jeśli metodą płatności jest karta kredytowa, czy metoda płatności powinna być używana tylko do obsługi zaimportowanych transakcji?

### <a name="expense-categories-and-shared-categories"></a>Kategorie wydatków i udostępniane kategorie

Gdy pracownicy tworzą raport wydatków, każdy zarejestrowany wydatek musi być skojarzony z kategorią wydatków. Kategorie wydatków pochodzą z kategorii udostępnionych, które mogą być udostępniane dla podmiotów prawnych w obrębie organizacji. Kategorie te również mogą być współużytkowane w zarządzaniu projektami i księgowaniu, w zależności od sposobu zdefiniowania danej organizacji. Na podstawie definicji organizacji i wskazówek zespołu implementacji określ, czy kategorie używane w zarządzaniu wydatkami będą używane tylko w zarządzaniu wydatkami lub czy powinny być udostępnione między zarządzaniem projektem a księgowością i zarządzaniem wydatkami. Pamiętaj, że te kategorie mogą być współużytkowane między projektami i wydatkami lub projektami i produkcją, ale nie między wydatkami i produkcją. Należy wybrać następujące decyzje dla każdej kategorii wydatków.

**Decyzje:**

- Jaka jest kategoria wydatków? Przykłady obejmują kategorie dla lotów, hoteli lub przebiegu.
- Czy kategoria wydatków jest również używana w zarządzaniu projektami i księgowaniu?
- Jaki jest typ wydatków?
- Jaka jest domyśla metoda płatności dla kategorii wydatków?
- Czy wydatki w kategorii wydatków muszą być wyszczególnione?
- Jaka jest główne konto domyślna dla kategorii wydatków?
- Jaka jest domyślna grupa podatków dla towaru w kategorii wydatków?
- Czy dozwolone są dodatkowe metody płatności dla kategorii wydatków? Jeżeli dozwolone są dodatkowe metody płatności, jakie są?
- Czy istnieją podkategorie w ramach tej kategorii wydatków? Jeżeli istnieją podkategorie, należy także pojąć następujące decyzje:

    - Czy jakakolwiek podkategorie są wykluczone ze zwrotu podatku?
    - Jaka jest grupa podatków dla towaru dotycząca podkategorii?

Jeśli kategoria wydatków jest również używana w zarządzaniu projektami i ich księgowaniu, odpowiedz na następujące pytania. W przeciwnym wypadku należy przejść do następujące sekcji.

- Jakie konta kosztów będą używane dla następujących wydatków?

    - Koszt
    - Alokacja listy płac
    - PWT — Wartość kosztu
    - Element kosztu
    - PWT — Wartość kosztu — Pozycja
    - Naliczona strata
    - PWT — Naliczona strata

- Jakie konta przychodów będą używane dla następujących elementów?

    - Zafakturowany przychód
    - Naliczony przychód — Wartość sprzedaży
    - PWT — Wartość sprzedaży
    - Naliczony przychód — Produkcja
    - PWT — produkcja
    - Naliczony przychód — Zysk
    - PWT — zysk
    - Naliczony przychód — Subskrypcja
    - PWT — subskrypcja

### <a name="taxes"></a>Podatki

W przypadku podatków związanych z podatkami trzeba określić, co jest uwzględnione lub dozwolone w raportach wydatków.

**Decyzje:**

- Czy podatek jest uwzględniony w kwotach wydatków?
- Czy zwrot z podatku powinien być dostępny dla wydatków?

    > [!NOTE]
    > Gdy planowano księgę główną, jeżeli zdecydowano o zastosowaniu amerykańskiego podatku i przepisów podatkowych, nie można włączyć zwrotu podatku dotyczącego wydatków. (Aby zastosować amerykański podatek i zastosować przepisów podatkowych, ustaw opcję **Zastosuj zasady opodatkowania dla podatku** na **Tak**.)

## <a name="policies"></a>Zasady

Tworząc zasady raportu wydatków można ułatwić organizacji oszczędność czasu i pieniędzy, gdy pracownicy ponoszą koszty w jej imieniu. Zasady gwarantują, że pracownicy mieszczą się w budżecie, podają wszystkie wymagane informacje i wydają pieniądze tylko wtedy, gdy jest to konieczne. Należy wybrać następujące decyzje dla każdej zasady raportu wydatków i każdej zasady zatwierdzenia raportu wydatków.

**Decyzje:**

- Jak nazywa się zasada?
- Do czego ma służyć zasada wydatków?
- Jeśli wcześniej zdecydowano o włączeniu wydatków międzyfirmowych, do jakich firm w organizacji odnosi się zasada?
- Kiedy zasad zaczyna obowiązywać?
- Kiedy zasad wygasa?
- Jaka jest reguła?
- Jaki jest wynik reguły?

