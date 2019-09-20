---
title: Usprawnione wprowadzanie pracowników i nawigacja
description: Wprowadzanie danych dla pracowników w Dynamics 365 for Talent zostało udoskonalone, aby umożliwić szybkie wprowadzanie dla wszystkich pracowników, przeszłych, aktywnych lub przyszłych. Uproszczony/skonsolidowany model nawigacji został zaktualizowany w celu szybkiego znajdowania informacji i wyświetlania i wprowadzania niezbędnych aktualizacji.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: be0253ffc4396f36050ef02c51a20d378e44473d
ms.sourcegitcommit: 4176c333ce3f88c5c68e95bd47e5791d32365dd2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1918217"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Usprawnione wprowadzanie pracowników i nawigacja

[!include [banner](includes/banner.md)]

Dynamics 365 for Talent umożliwia wydajne wprowadzanie danych dotyczących pracowników i zatrudnienia. Można szybko zaktualizować informacje o historii pracy dla przeszłych, aktywnych i przyszłych pracowników i zleceniobiorców.

Można również włączyć uproszczone funkcje nawigacyjne, aby szybko znajdować informacje związane z informacjami i wprowadzać niezbędne zmiany. Ta funkcja jest teraz dostępna w środowiskach piaskownicy. Aby włączyć tę funkcję, przejdź do **Administrowanie systemem > Łącza > Ustawienia > Parametry systemowe > Funkcje w wersji zapoznawczej**. Wybierz **Formularz i nawigację rozszerzonego pracownika**. Dzięki temu zmiany są włączone dla wszystkich użytkowników. Opcję tę można wyłączyć w dowolnym momencie.

## <a name="view-options"></a>Opcje widoku

**Opcje widoku** w formularzu pracownik umożliwiają wybranie kombinacji pracowników i zleceniobiorców z jednej listy. Te opcje umożliwiają wyświetlanie pracowników w różnych firmach lub na potrzeby aktualnie zalogowanego podmiotu prawnego. Można również wyświetlać aktywnych, oczekujących i zamkniętych pracowników, a także ograniczyć wyniki na podstawie typu pracownika (pracownika lub zleceniobiorcy). Jeśli jest włączone zaawansowane zabezpieczenia, będą widoczni tylko pracownicy i zleceniobiorcy w firmach, do których masz dostęp.

Kolumny w widoku listy zmieniają się w zależności od wybranych opcji. Na przykład podczas przeglądania pracowników końcowych daty zakończenia i kodów przyczyn są wyświetlane jako dodatkowe kolumny na liście. 

[![Opcje widoku](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Nawigacja i transparent

Na transparencie są wyświetlane kluczowe informacje dotyczące każdego pracownika. Transparent dla aktywnych pracowników wyświetla następujące pola:

- **Nazwa**
- **Dział**
- **Typ stanowiska**
- **Typ pracownika**
- **Menedżer**
- **Firma**

Transparent dla pracowników, którzy opuścili firmę wyświetla następujące pola:

- **Data zakończenia**
- **Przyczyna**

Transparent dla pracowników, którzy są w trakcie wdrażania, wyświetla następujące pola:

- **Nazwa**
- **Dział**
- **Typ stanowiska**
- **Menedżer**
- **Data rozpoczęcia**
- **Firma**

Okienko akcji strony pracownik zostało ponownie zorganizowane w celu uwzględnienia mniejszej liczby opcji. Informacje są teraz zorganizowane w następujących kategoriach: 

- Roboczy
- Osoba
- Opuść
- Kompensacja
- Świadczenia
- Zgodność z przepisami

Ponadto nowa karta **Łącza** na głównej stronie pracownika daje użytkownikom centralną lokalizację, aby uzyskać dostęp do wszystkich pokrewnych informacji dotyczących pracownika.

Ze względu na te zmiany informacje mogą pojawiać się w lokalizacji innej niż używana w systemie. Na przykład informacje o liście płac, które poprzednio były wyświetlane w formularzu pracownika, są teraz wyświetlane w okienku akcji pod **Kompensacja > Lista płac**, a karta **Dane osobowe** ma teraz przycisk **Więcej informacji**, aby ukryć pola, które nie są często używane.

[![Transparent](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Historia pracy

Na karcie **Historia pracy** jest wyświetlana historia pracy dla wszystkich firm i dostępna dla pracowników najemnych, aktywnych i oczekujących oraz zleceniobiorców. Teraz można wyświetlić całą historię pracy na raz dla firm, do których masz dostęp. Ponadto można edytować informacje dla każdego wpisu historii pracy bez zmiany kontekstu danych. Wszystkie informacje można zaktualizować bezpośrednio na stronie. 

[![Historia pracy](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Historia stanowisk

Karta **Stanowiska** na głównej stronie pracownika stanowi pełny widok wszystkich stanowisk znajdujących się w organizacji, w tym w przeszłości, obecnie i dla dowolnego przyszłego zlecenia. Można również przejść bezpośrednio do historii stanowisk pracownika w okienku akcji.

[![Pozycje](./media/Worker-position-history.png)](./media/Worker-position-history.png)

