---
title: Konfigurowanie parametrów rozwiązania Human Resources
description: W tym temacie wyjaśniono, jak skonfigurować parametry specyficzne dla firmy w Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 476f44c665adb2918e7cd882d4ea873b4b4f94fa33a74dc96d3eccc74b676ce5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739258"
---
# <a name="configure-human-resources-parameters"></a>Konfigurowanie parametrów rozwiązania Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Niektóre parametry modułu Zasobów ludzkich są wspólne dla wielu firm, podczas gdy inne parametry są specyficzne dla firm. W tym temacie wyjaśniono, jak skonfigurować parametry Zasobów ludzkich.

Do ustawiania parametrów Zasobów ludzkich służą dwie strony. W przypadku parametrów współużytkowanych przez firmy, użyj strony **Udostępniane parametry zasobów ludzkich**. W przypadku parametrów specyficznych dla firmy (ustawienie dotyczy tylko jednej firmy), użyj strony **Parametry zasobów ludzkich**.

![Przejdź do parametrów zasobów ludzkich.](./media/hr-employee-self-service-human-resources-parameters.png)

Na stronie **parametrów zasobów ludzkich** ustawienia są podzielone na sześciu kartach:

- **Ogólny**
- **Rekrutacja** (tej karty nie ma w aplikacji Dynamics 365 Human Resources)
- **Kompensacja**
- **Sekwencje identyfikatorów**
- **FMLA**
- **Samoobsługa pracownika etatowego**
- **Samoobsługa menedżera**
- **Zarządzanie świadczeniami**
- **Urlopy i nieobecności**
- **Metody płatności**

Każda karta zawiera informacje dotyczące jednej firmy.

## <a name="general"></a>Ogólny

Ustawienia wprowadzone na karcie **Ogólne** definiują wygląd informacji o nieobecności, urazach, chorobach i zatrudnianiu nowych pracowników. Ustawienia na tej karcie definiują także niektóre domyślne wpisy pojawiające się podczas pracy. W szczególności ta karta umożliwia:

- Wybierz kolor, który ma być zastosowany do otwartych transakcji nieobecności.
- Umożliwia określenie arkusza stylów, który będzie używany dla raportów.
- Włącz integrację między kursami szkoleniowymi a rejestracją nieobecności.
- Umożliwia wybranie kodu nieobecności używanego do kontrolowania tej integracji.
- Wskaż, jak długo mają utrzymywać się przypadki obrażeń i chorób.
- Umożliwia określenie domyślnego numeru identyfikacyjnego wyświetlanego podczas zatrudniania nowego pracownika.
- Określ datę używaną do obliczania lat pracy. 

![Karta Ogólne.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Rekrutacja

Ustawienia na karcie **Rekrutacja** określają typy dokumentów używane do korespondencji automatycznie wysyłanej do kandydatów. Można także wskazać projekt rekrutacji używany dla niechcianych zgłoszeń.

Okres zdefiniowany dla wiekowania projektu rekrutacji określa projekty rekrutacji uwzględnione w kafelku **Projekty wiekowania** w obszarze roboczym **Zarządzanie rekrutacją**. Okres zdefiniowany dla ostrzeżenia o ostatecznym terminie zgłoszenia jest używany do wyświetlania projektów rekrutacji, których ostateczny termin zgłoszeń się zbliża i jest określony w kafelku **Zbliża się ostateczny termin zgłoszenia** w obszarze roboczym **Rekrutacja**.

Aby uzyskać więcej informacji o rekrutacji, zobacz temat [Rekrutowanie kandydatów do pracy](hr-personnel-recruit.md).

## <a name="compensation"></a>Kompensacja

W Dynamics 365 Finance ustawienia wprowadzone na karcie **Wynagrodzenie** określają, czy użytkownicy muszą potwierdzać, że chcą zapisać informacje dla systemu wynagrodzeń o stałej lub zmiennej wysokości. W wybrania **Włącz weryfikację zapisu** kiedy użytkownik zamknie stronę związaną z wynagrodzeniami, otrzyma wiadomość z zapytaniem, czy chce zapisać rekord. Niektóre strony w module Zarządzania wynagrodzeniami nie zezwalają na usuwanie informacji. Dzięki pytaniu użytkowników, czy chcą zapisać informacje, można ograniczyć ilość zapisywanych danych, których potem nie można usunąć. Jeśli pole wyboru **Włącz weryfikację zapisu** nie jest zaznaczone, rekordy będą natychmiast zapisywane, być może zanim użytkownik będzie gotowy. W przypadku korzystania z funkcji Zarządzania wydajnością można wybrać model oceniania na karcie **Wynagrodzenie** zamiast modelu przypisanego do systemów wynagrodzeń przy ocenie wydajności.

W obszarze Zasoby ludzkie można użyć karty **Wynagrodzenie**, aby ograniczyć dostęp do planów wynagrodzeń i ustawić walutę domyślną.

Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz [Omówienie planów wynagrodzeń](hr-compensation-overview.md).

![Karta Wynagrodzenie.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Sekwencje identyfikatorów

Ustawienia na karcie **Sekwencja numerów** decydują o sekwencjach używanych do automatycznego przypisywania identyfikatorów do towarów w zasobach ludzkich, takich jak:

- Aplikacje
- Rejestracje nieobecności
- Wyniki procesu związanego z wynagrodzeniem
- Numery przypadków
- Kursy
- Programy kursów

Aby obsługiwać odwołania numeracji i kody, użyj strony listy **Sekwencje identyfikatorów** (wybierz **Administrowanie organizacją > Sekwencje identyfikatorów > Sekwencje identyfikatorów**).

Aby uzyskać więcej informacji, zobacz temat [Omówienie sekwencji identyfikatorów](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> Liczba przepracowanych godzin nie może przekroczyć 1250, a staż pracy nie może przekroczyć 12 miesięcy. Te maksymalne wartości są zgodne z prawem federalnym w Stanach Zjednoczonych.

![Karta Sekwencje numerów.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

Na karcie FMLA są ustawiane wymagania dotyczące uprawnień FMLA i godziny uprawnień FMLA. Aby uzyskać więcej informacji, zobacz [Konfigurowanie parametrów urlopu i nieobecności](hr-leave-and-absence-parameters.md).

![Karta FMLA.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Samoobsługa pracownika etatowego

Ustawienia na karcie **Samoobsługa pracownika etatowego** mają wpływ na sposób, w jaki samoobsługa pracownika etatowego jest wyświetlana pracownikom etatowym. Na tej karcie można:

- Wprowadź nazwę obszaru roboczego samoobsługi pracownika
- Wybierz, jakie informacje menedżer może wprowadzić dla pracowników
- Dodawanie przydatnych łączy dla pracowników
- Zablokuj pracownikom możliwość dodawania lub edytowania biznesowych danych kontaktowych. Aby uzyskać więcej informacji, zobacz temat [Ogranicz edycję danych osobowych](hr-employee-self-service-restrict-editing.md).

Aby uzyskać więcej informacji dotyczących konfigurowania funkcji samoobsługi pracowników etatowych, zobacz [Omówienie samoobsługi dla pracownika etatowego i menedżera](hr-employee-manager-self-service-overview.md).

![Karta Samoobsługa pracownika etatowego.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Samoobsługa menedżera

Ustawienia na karcie **Samoobsługa menedżera** wpływają na to, co menedżerowie widzą w samoobsługi menedżera. Na tej karcie można skonfigurować następujące opcje:

- Zakres wygasających rekordów
- Informacje, które menedżerowie mogą wyświetlać w wygasających rekordach
- Określa, czy menedżerowie mogą wyświetlać otwarte stanowiska w raportach rozszerzonych
- Widoki odchodzących pracowników
- Przydatne łącza dla menedżerów

Aby uzyskać więcej informacji dotyczących konfigurowania funkcji samoobsługi menedżerów, zobacz [Omówienie samoobsługi dla pracownika etatowego i menedżera](hr-employee-manager-self-service-overview.md).

![Karta Samoobsługa menedżera.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Zarządzanie świadczeniami

Na karcie Zarządzanie świadczeniami możesz skonfigurować opcje poczty e-mail dotyczące zarządzania świadczeniami. Aby uzyskać więcej informacji na temat konfiguracji i użytkowania funkcji Zarządzanie świadczeniami, zobacz [Zarządzanie świadczeniami - omówienie](hr-benefits-management-overview.md).

![Karta Zarządzanie świadczeniami.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Urlopy i nieobecności

Aby uzyskać więcej informacji dotyczących konfigurowania i korzystania z Urlopów i nieobecności, zobacz [Zarządzanie urlopami i nieobecnościami](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Metody płatności

Na karcie **Metody płatności** możesz wybrać metody płatności obsługiwane przez organizację. Aby uzyskać więcej informacji o konfiguracji planów wynagrodzeń, zobacz [Omówienie planów wynagrodzeń](hr-compensation-overview.md).

![Karta Metody płatności.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
