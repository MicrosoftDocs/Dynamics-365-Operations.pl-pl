---
title: "Przegląd zarządzania pracownikami"
description: "W tym temacie opisano sposób korzystania z usługi Zarządzanie pracownikami (WFM) w celu użycia znanych klientów punktu sprzedaży (POS), Modern POS i Cloud POS, aby ułatwić menedżerom sklepów zarządzanie pracownikami."
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="workforce-management-overview"></a>Przegląd zarządzania pracownikami

[!include[banner](includes/banner.md)]
    
Usługa Zarządzanie pracownikami (WFM) wykorzystuje znanych klientów punktu sprzedaży (POS), Modern POS i Cloud POS, aby umożliwić menedżerom sklepów zarządzanie pracownikami. Usługa WFM wykorzystuje platformę rozszerzeń do pobrania odpowiednich pakietów w punkcie sprzedaży. Te pakiety są pobierane po zamknięciu i ponownym otwarciu punktu sprzedaży. Dlatego, gdy firma Microsoft opublikuje nowe funkcje dla usługi WFM, należy zamknąć i ponownie otworzyć aplikację punktu sprzedaży.

Korzystając z tej usługi menedżerowie sklepów mogą łatwo tworzyć i publikować tygodniowe plany robocze dla swoich sklepów. Pracownicy sklepów mogą następnie szybko wyświetlić własne plany i plany współpracowników. Dzięki temu mogą się dowiedzieć, z kim będą pracować podczas przydzielonych zmian. Pracownicy sklepów mogą także tworzyć wnioski o nieobecność, zamianę zmiany i oferty zmian. Wszystkie te wnioski uruchamiają zdefiniowany przepływ pracy.

Podczas zmiany pracownicy sklepów mogą korzystać z funkcji rejestracji godziny wejścia i wyjścia dostępnej w klientach punktu sprzedaży. Dane są następnie przesyłane do centrali w celu przetworzenia listy płac. Funkcja rejestracji godziny wejścia i wyjścia to istniejąca cecha punktu sprzedaży. Więcej informacji o konfiguracji obsługiwanych scenariuszy zawiera temat [Godzina wejścia i wyjścia](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Obsługiwane scenariusze
Ta sekcja zawiera więcej informacji o obsługiwanych scenariuszach.

- **Tworzenie i publikowanie harmonogramów** — usługa WFM wykorzystuje uprawnienia punktu sprzedaży skonfigurowane w centrali do określenia, czy pracownik ma uprawnienia menedżera sklepu. Tylko menedżerowie sklepów mogą tworzyć i publikować harmonogramy przy użyciu operacji Zarządzanie harmonogramem. Mogą szybko utworzyć harmonogram, kopiując i wklejając istniejące zmiany między pracownikami. Mogą także tworzyć harmonogram, importując go z poprzedniego do bieżącego tygodnia.

    Jeżeli harmonogram nie jest opublikowany, jest w stanie roboczym i wygląda inaczej niż opublikowany harmonogram. Menedżerowie sklepów mogą opublikować harmonogram, klikając przycisk **Opublikuj** dla dowolnego tygodnia. Po opublikowaniu harmonogramu tygodnia wszystkie zmiany są publikowane automatycznie. Przykłady zmian to dodanie lub usunięcie zmian roboczych lub nieobecności albo edycje zmian roboczych lub nieobecności. Pracownicy sklepów mogą wyświetlać tylko te harmonogramy, które zostały opublikowane dla różnych tygodni.
    
- **Tworzenie i zatwierdzanie żądań** — pracownic sklepów mogą tworzyć trzy typy żądań:

    - Wniosek urlopowy
    - Wniosek o zamianę zmiany
    - Wniosek o ofertę zmiany

    Te wnioski mogą być tworzone za pomocą operacji Planowanie żądań. Każde żądanie jest wykonywane zgodnie ze zdefiniowanym przepływem pracy, a pracownicy mogą łatwo sprawdzić stan swoich żądań.
    
    Wnioski urlopowe są automatycznie wysyłane do menedżera sklepu w celu zatwierdzenia. Jeżeli istnieje kilku menedżerów sklepów, wszyscy menedżerowie mogą wyświetlić dany wniosek, ale tylko jeden może go zatwierdzić lub odrzucić. Typy nieobecności są skonfigurowane w centrali handlu detalicznego na stronie **Typy urlopów i nieobecności** w module **Sprzedaż detaliczna**. Po zatwierdzeniu lub odrzuceniu przez menedżera sklepu żądanie jest przenoszone na kartę **Historia** dla operacji Planowanie żądań.
    
    Żądanie zamiany zmiany lub oferty zmiany najpierw przechodzi do pracownika, do którego wysłano żądanie. Menedżer sklepu może wyświetlić żądanie dopiero po zatwierdzeniu go przez tego pracownika. Dlatego, jeżeli pracownik odrzuci żądanie zamiany zmiany lub oferty zmiany, menedżer nie może go wyświetlić. Pracownik, który utworzył żądanie może je także anulować zanim menedżer zatwierdzi je lub odrzuci.

- **Pokaż aktywnych pracowników sklepu w widoku harmonogramu** — po dodaniu pracownika do sklepu, na przykład przez skojarzenie go z książką adresową pracownika sklepu, pracownik jest dostępny do planowania w usłudze WFM. W centrali uruchamiane jest cykliczne zadanie wsadowe o nazwie **Przetwarzanie danych pracownika na potrzeby zarządzania pracownikami**. To zadanie przygotowuje skojarzenia pracownika sklepu, które zostaną wysłane do usługi Common Data Service (CDS).

    Ten sam proces jest używany po usunięciu pracownika ze sklepu. Jednakże usunięty pracownik jest nadal widoczny dla przeszłych, bieżących i przyszłych tygodni, jeżeli jest do niego przypisana aktywna zamiana zmiany lub nieobecność. Dlatego do momentu usunięcia tych zamian zmiany i nieobecności usunięty pracownik będzie nadal widoczny w tych tygodniach.

