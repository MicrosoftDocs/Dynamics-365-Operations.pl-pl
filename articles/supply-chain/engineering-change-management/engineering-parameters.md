---
title: Parametry zarządzania zmianami projektowymi
description: W tym temacie opisano sposób konfigurowania funkcji zarządzania zmianą inżynieryjną wersji zapoznawczej aplikacji Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 0cf0e56a8aece98379aa0f181d7b7ff665767544
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435676"
---
# <a name="engineering-change-management-parameters"></a>Parametry zarządzania zmianami projektowymi

[!include [banner](../includes/banner.md)]

Na **stronie parametry zarządzania zmianami inżynieryjnymi** znajdują się parametry ustawień, które zmieniają domyślne zachowanie związane z procesami zarządzania wersjami produktów i zarządzaniem zmianami inżynieryjnymi.

## <a name="open-the-engineering-change-management-parameters-page"></a>Otwórz stronę Parametrów zarządzania zmianami inżynieryjnymi

Aby otworzyć **stronę parametry zarządzania zmianami inżynieryjnymi**, przejdź do **Zarządzanie zmianami inżynieryjnymi \> Konfiguracja \> Parametry zarządzania zmianami inżynieryjnymi**. Następnie można tak skonfigurować pola, jak to opisano w pozostałych sekcjach tego tematu.

## <a name="release-control-tab"></a>Kontrola zwolnienia — karta

W poniższej tabeli opisano pola dostępne na karcie **Kontrola zwolnienia** na stronie **Parametry zarządzania zmianami inżynieryjnymi**. Te pola wpływają na proces struktury zwalniania produktu.

| Pole | opis |
|---|---|
| Reguła numeru pozycji | Umożliwia wybranie sposobu definiowania numeru pozycji, gdy produkt jest zwalniany do firmy. Wybierz *numer produktu inżynierskiego*, jeśli numer produktu w firmie przyjmującej powinien jest zgodny z numerem produktu w firmie inżynierskiej. Wybierz pozycję *lokalna sekwencja numerów pozycji*, jeśli produkt powinien przyjąć kolejny numer z sekwencji numerów produktów w firmie. |
| Reguły nazwy BOM | Umożliwia wybranie sposobu definiowania nazwy BOM w czasie, gdy produkt jest odbierany (zwolniony) w firmie. Umożliwia wybór *nazwy technologicznej* lub *numeru przyjęcia towaru*. |
| Reguła nazwy marszruty | Umożliwia wybranie sposobu definiowania nazwy BOM w czasie, gdy produkt jest odbierany (zwolniony) w firmie. Umożliwia wybór *nazwy technologicznej* lub *numeru przyjęcia towaru*. |
| Uruchom kontrolę BOM | Umożliwia określenie, czy czek BOM będzie uruchamiany, gdy produkt zostanie odebrany (zwolniony) w firmie. |
| Zachowanie przy zwalnianiu w przypadku nieaktywnego BOM | Umożliwia określenie, czy produkt może być zwolniony, jeśli ma nieaktywny BOM. Wybierz opcję *Akceptuj*, *tylko ostrzeżenie* lub *niedozwolone*. |
| Zachowanie przy zwalnianiu w przypadku nieaktywnej marszruty | Umożliwia określenie, czy produkt może zostać zwolniony, jeśli trasa jest nieaktywna. Wybierz opcję *Akceptuj*, *tylko ostrzeżenie* lub *niedozwolone*.|
| Akceptacja produktu | Umożliwia określenie, czy przed zwolnieniem produktu w firmie będzie wymagany dodatkowy krok akceptacji. Wybierz opcję *ręcznie*, aby dodać krok akceptacji. W takim przypadku na stronie **otwarte wersje produktów** są wyświetlane produkty. Wybranie opcji *automatycznie* powoduje wyświetlenie produktu bezpośrednio na **stronie zwolnione produkty** w docelowej firmie bezpośrednio po zwolnieniu produktu wraz z jego strukturą produktów zwolnienia. |

## <a name="engineering-change-management-tab"></a>Karta Zarządzanie zmianami projektowymi

W poniższej tabeli opisano pola dostępne na **karcie Zarządzanie zmianami inżynieryjnymi na stronie** **parametry zarządzania zmianami inżynieryjnymi**. Te ustawienia wpływają na proces zarządzania zmianami inżynierskimi.

| Pole | opis |
|---|---|
| Kategoria | Kategoria domyślna, która będzie używana podczas tworzenia żądania zmiany inżynierskiej. |
| Priorytet | Domyślny priorytet, który będzie używany podczas tworzenia żądania zmiany inżynierskiej. |
| Reguła ważności | Umożliwia wybranie sposobu ustanawiania wagi zlecenia zmiany inżynieryjnej. Jeśli użytkownik oczekuje na wprowadzenie wartości w polu **Ważność**, należy wybrać opcję *ręcznie*. Wybierz opcję *Oblicz* aby system obliczał wartość pola **Ważność** po wybraniu opcji **Oblicz ważność** w okienku akcji w żądaniu zmiany inżynieryjnej. W takim przypadku system będzie używał reguł ważności zdefiniowanych na **stronie zestawów reguł ważności**. Wybierz opcję *Oblicz automatycznie* aby wartość **pola ważności** była automatycznie obliczana i wypełniana zgodnie z zestawami reguł ważności. |
| Ponowne zwolnienie produktów objętych wpływem | To pole jest używane podczas ponownego wydawania produktów za pośrednictwem zlecenia zmiany inżynierskiej. W oknie dialogowym **zwalnianie** można określić, czy mają być proponowane wszystkie produkty, czy tylko produkty, których dotyczy problem. |
| Poziomy BOM do zwolnienia | Głębokość poziomu BOM do wydania. Jeśli BOM ma więcej poziomów (o ile jest głębszy) niż wartość określona w tym miejscu, zostaną zwolnione tylko poziomy określone przez określoną wartość. |
