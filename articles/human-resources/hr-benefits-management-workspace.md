---
title: Obszar roboczy zarządzania świadczeniami
description: W tym artykule opisano obszar roboczy Zarządzanie świadczeniami w rozwiązaniu Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7975d1723e07ae390961d4f44e0f34f2ff2df44d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902926"
---
# <a name="benefits-management-workspace"></a>Obszar roboczy zarządzania świadczeniami


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

W tym artykule opisano obszar roboczy **Zarządzanie świadczeniami** w rozwiązaniu Dynamics 365 Human Resources.

> [!NOTE]
> Aby wyświetlić obszar roboczy **Zarządzanie świadczeniami**, należy najpierw włączyć funkcję **obszaru roboczego Zarządzanie świadczeniami (wersja zapoznawcza)** w zarządzaniu funkcjami. Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).<br><br>![Włącz obszar roboczy zarządzania świadczeniami.](./media/hr-benefits-management-workspace-enable.png)

Obszar roboczy **Zarządzanie świadczeniami** umożliwia szybki widok elementów świadczeń, które wymagają Twojej uwagi. Na tej stronie możesz zobaczyć:

- Sumy pozycji oczekujących na działanie
- Pracownicy z niepotwierdzonymi wyborami
- Pracownicy, którzy niedawno zapisali się na świadczenia
- Pracownicy z przyszłymi zdarzeniami życiowymi
- Nowi zatrudnieni, którzy nie są zapisani
- Pracownicy z trwającymi zdarzeniami życiowymi
- Pracownicy z otwartymi rejestracjami, którzy nie wybrali żadnych planów

![Obszar roboczy zarządzania świadczeniami.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Wyświetlanie elementów akcji

Możesz wyświetlić swoje działania, wybierając kafelek lub kartę. Jeśli wybierzesz kartę, możesz wyświetlać i wybierać pracowników bezpośrednio na stronie obszaru roboczego.

![Elementy akcji.](./media/hr-benefits-management-workspace-action-items.png)

W przypadku wybrania kafelka przejdź na stronę z tym obszarem. Na przykład wybranie dowolnej z tych kafelków powoduje wyświetlenie strony **Plany świadczeń pracownika** odfiltrowanych dla pracowników, na których musisz podjąć działania:

- **Niepotwierdzone wybory**
- **Otwieranie rejestracji bez wyewidencjonowanych planów**
- **Zarejestrowani w świadczeniach**
- **Nowo zatrudniona osoba nie została zarejestrowana**

![Plany świadczeń pracowniczych.](./media/hr-benefits-management-workspace-plans.png)

Wybieranie **Trwającego zdarzenia życiowego** lub **Przyszłego zdarzenia życiowego** umożliwia dostęp do listy aktywnych lub przyszłych zdarzeń.

![Zdarzenia zmiany sytuacji życiowej.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Przetwarzanie

Aby przetworzyć uprawnienia do rejestracji, zdarzenia z życia lub aktualizacje zmian stawek, wybierz odpowiednią pozycję na pasku nawigacyjnym.

![Przetwarzanie.](./media/hr-benefits-management-workspace-processing.png)

Aby wyświetlić wyniki przetwarzania, wybierz **Wyniki procesu** na stronie.

![Wyniki procesu.](./media/hr-benefits-management-workspace-process-results.png)

Aby uzyskać więcej informacji na temat przetwarzania świadczeń, zobacz:

- [Przetwarzanie uprawnień do rejestracji](hr-benefits-process-enrollment-eligibility.md)
- [Przetwarzanie zmian zdarzeń zmiany sytuacji życiowej](hr-benefits-process-life-event-changes.md)
- [Przetwarzanie uprawnień zdarzeń zmiany sytuacji życiowej](hr-benefits-process-life-event-eligibility.md)
- [Przetwarzanie zdarzeń zmiany sytuacji życiowej](hr-benefits-process-life-events.md)
- [Przetwarzanie zmian stawek](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Zmień okres

Aby wyświetlić inny okres świadczeń, wybierz go z listy rozwijanej **Okres**.

![Zmień okres.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Otwórz kartę rejestracji

Możesz wyświetlić czynności do wykonania, wybierając kafelek lub kartę. Jeśli wybierzesz kartę, możesz wyświetlić i wybrać pracowników na stronie obszaru roboczego.
Karta **Otwórz rejestrację** zawiera kluczowe mierniki otwartego procesu rejestracji. 

Informacje dotyczące rejestracji otwartej zostaną wyświetlone na 30 dni przed **datą rozpoczęcia rejestracji**. Jest to definiowane w konfiguracji **okresów** w formularzu **Zarządzanie świadczeniami** > **Łącza** > **Okresy**, w polu **Data początku rejestracji**.  Aby zmienić to ustawienie, przejdź do **Parametry współdzielone Human resources** > **Zarządzanie świadczeniami** > **Otwórz opcje rejestracji** i zaktualizuj pole **Liczba**.  

Na karcie **Otwórz rejestrację** są dostępne następujące informacje:
 - Pracownicy, którzy nie rozpoczęli otwartego procesu rejestracji
 - Pracownicy z wyborami w trakcie przetwarzania
 - Pracownicy, którzy przeszli proces wyborczy
 - Niepotwierdzone wybory

**Kafelki podsumowania**

- **Nie rozpoczęto** — w kafelku **Nie rozpoczęto** jest przedstawiana liczba pracowników, którzy nie uruchomili procesu rejestracji. Kafelek **Nie rozpoczęty** to filtrowana lista, która pokazuje tylko tych pracowników, którzy nie mają wybranych planów, uchyleń lub wyewidencjonowanych dla otwartego okresu planu rejestracji. Plany obowiązkowe są ignorowane i nie uwzględniane, ponieważ są domyślnie wybrane dla pracownika.  Można przejść do szczegółów tego kafelka, aby wyświetlić listę pracowników, którzy nie uruchomili otwartego procesu rejestracji, na stronie **Plan świadczeń pracownika**.

  > [!NOTE]
  > Jeśli nie chcesz śledzić otwartego postępu rejestracji dla **typu planu**, możesz wykluczyć go, przechodząc do pola **Zarządzanie świadczeniami** > **Łącza** > **parametry samoobsługi pracownika** > **Ustawienia kafelków planów świadczeń** i aktualizować pole **Postęp otwartej rejestracji śledzenia**.  Mogą być na przykład tworzone **Typ planu** = **Inne**. Te plany mogą być planami opcjonalnymi, dla których nie chcesz śledzić postępu rejestracji. Jeśli nie wybierzesz tego typu planu, plany tego typu będą ignorowane podczas śledzenia postępu lub zakończenia rejestracji na **karcie Otwarta rejestracja**. To ustawienie dotyczy typu planu wybranego dla wszystkich okresów i firm.

- **W toku** — kafelki **w toku** dają liczbę pracowników z wyborami w toku. Kafelek **W toku** jest listą filtrowaną, która zawiera tylko pracowników, którzy mają co najmniej jeden plan, który jest uchylony lub wybrany. Plany obowiązkowe są ignorowane i nie uwzględniane, ponieważ są domyślnie wybrane dla pracownika. Można przejść do szczegółów tego kafelka, aby wyświetlić wybrane i uchylone plany na stronie **Zbiorcze aktualizowanie planów świadczeń pracowników**.

- **Zarejestrowane świadczenia** — kafelek **Zarejestrowane świadczenia** podaje liczbę pracowników, którzy są w pełni zarejestrowani w świadczeniach. Kafelek **Zarejestrowane w świadczeniach** to przefiltrowana lista, która pokazuje pracowników, którzy wybrano lub uchylono wszystkie plany. Kwerenda wyklucz plany, które nie są śledzone w celu otwartej rejestracji na stronie **Parametry samoobsługi pracownika**. Można przejść do szczegółów z tego kafelka, aby wyświetlić listę pracowników na stronie **Plany świadczeń pracownika**.

- **Niepotwierdzone wybory** – W kafelku **Niepotwierdzone wybory** jest przedstawiana liczba pracowników, którzy mają plany, które zostały wybrane lub uchylone i muszą zostać potwierdzone. Możesz przejść wstecz z tego kafelka, aby wyświetlić stronę **Zbiorcza aktualizacja planów świadczeń pracowniczych**.

**Działanie**

- **Nie rozpoczęto** — karta **Nie rozpoczęto** wyświetla listę pracowników, którzy nie rozpoczęli procesu rejestracji. Kafelek **Nie rozpoczęto** to filtrowana lista, która pokazuje tylko tych pracowników, którzy nie mają wybranych planów, uchyleń lub wyewidencjonowanych dla otwartego okresu planu rejestracji. Plany obowiązkowe są ignorowane i nie uwzględniane, ponieważ są domyślnie wybrane dla pracownika. Można przejść do szczegółów pracownika, aby wyświetlić stronę **szczegółów planów świadczeń pracownika**.

- **Wybory w toku** — karta **Wybory w toku** wyświetla listę pracowników, którzy mają trwające wybory. Kafelek **Wybory w toku** jest listą filtrowaną, która zawiera tylko pracowników, którzy mają co najmniej jeden plan, który jest uchylony lub wybrany. Plany obowiązkowe są ignorowane i nie uwzględniane, ponieważ są domyślnie wybrane dla pracownika. Można przejść do szczegółów pracownika, aby wyświetlić stronę **szczegółów planów świadczeń pracownika**.

## <a name="view-more-options"></a>Wyświetl więcej opcji

Aby wyświetlić więcej informacji lub dodatkowe czynności, wybierz **Łącza**.

![Linki.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie zarządzania świadczeniami](hr-benefits-management-overview.md)
