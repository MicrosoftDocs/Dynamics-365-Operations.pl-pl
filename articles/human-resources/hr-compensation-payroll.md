---
title: Gotowe do wypłaty
description: W tym temacie pokazano, jak oznaczyć pracownika jako gotowego do zapłaty w Dynamics 365 Human Resources.
author: marcelbf
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 80bba5446eb7a87d96a7da4ae856cb5ca114ce52
ms.sourcegitcommit: 24e20b3b96834b23311f1bf5dbab28baf3323728
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483789"
---
# <a name="ready-to-pay"></a>Gotowe do wypłaty

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> Jeśli chcesz oznaczyć pracownika jako gotowego do zapłaty, musisz najpierw włączyć funkcję **(wersja zapoznawcza) integracji listy płac** w zarządzaniu funkcjami. Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).

Ta funkcja umożliwia specjalistom ds. zasobów ludzkich zrozumienie, którzy pracownicy są gotowi do przetwarzania listy płac, a którzy wymagają działania, zanim zostaną wykorzystane przez zewnętrznego dostawcę listy płac.

## <a name="mark-employee-as-ready-to-pay"></a>Oznaczanie pracownika etatowego jako gotowego do wypłaty

Zbieranie i weryfikacja informacji o pracownikach może być czasochłonne i podatne na błędy. Zapewniając specjalistom ds. zasobów ludzkich możliwość przeglądania i łatwej aktualizacji informacji o pracownikach, Dynamics 365 Human Resources pomaga skrócić czas poświęcony na przygotowanie do przetwarzania listy płac.

Oznaczanie pracownika etatowego jako gotowego do wypłaty:

1. Otwórz **Zarządzanie wynagrodzeniami**. W obszarze roboczym znajdują się dwa kafelki: 
    - **Pracownicy etatowi gotowi do wypłaty**
    - **Pracownicy nie są gotowi do zapłaty**
    ![Obszar roboczy zarządzania wynagrodzeniami.](./media/hr-ready-to-pay-1-workspace.png)

2. Wybierz kafelek **Pracownicy nie są gotowi do zapłaty**.

3. Wybierz pracowników, którzy mają zostać zweryfikowani. Na karcie **Listy płac** w grupie **Gotowe do zapłaty** wybierz pozycję **Sprawdź poprawność**.
    ![Zweryfikuj pracowników.](./media/hr-ready-to-pay-2-validate.png)

4. Aby przejrzeć wyniki, na karcie **Listy płac** w grupie **Gotowe do zapłaty** wybierz pozycję **Wyniki**.

## <a name="validation"></a>Weryfikacja

Przed oznaczeniem pracownika jako gotowego do zapłaty, profil pracownika zostanie zweryfikowany pod kątem kompletności.

![Sprawdzanie poprawności wyników.](./media/hr-ready-to-pay-3-results.png)

| Weryfikacja | Szczegóły |
| --- | --- |
| **Parametr celu adresu** | Sprawdza poprawność, czy parametr **Użyj adresów listy płac w celu** jest włączony. |
| **Adres listy płac** | Sprawdza, czy profil pracownika ma co najmniej jeden adres z przeznaczeniem **Lokalizacja miejsca zamieszkania listy płac** lub **Lokalizacja pracy listy płac** i istnieje tylko jeden adres na cel. |
| **Zatrudnienie** | Sprawdza, czy pracownik ma co najmniej jedno zatrudnienie (obecne, poprzednie lub przyszłe). |
| **Numer identyfikacyjny** | Sprawdza, czy parametr **Użyj typów identyfikacji w przetwarzaniu listy płac** ma wartość **tak** na stronie **Parametry Human resources** i czy typ identyfikacji wskazany w parametrze jest wypełniony w profilu pracownika. |
| **Imię i nazwisko** | Potwierdza, że pola **Imię** i **Nazwisko** są wypełnione.|
| **Umieszczenie** | Sprawdza, czy pracownik ma przypisane stanowisko. |
| **Data urodzenia** | Pole **Urodziny** jest wypełnione. |
| **Kompensata** | Sprawdza, czy pracownik jest zapisany do planu stałego wynagrodzenia. |

Jeśli jedna z tych walidacji się nie powiedzie, nie możesz oznaczyć pracownika jako gotowego do zapłaty.

Jeśli pole **Gotowe do zapłaty** to **Nie**, oznacza to, że należy wykonać akcję, aby upewnić się, że profil pracownika jest ukończony. Nie zatrzyma to ujawnienia danych w jakiejkolwiek jednostce danych. 

## <a name="known-issues"></a>Znane problemy

- Należy wyłączyć funkcję **Usprawniony wpis pracownika** w zarządzaniu funkcjami. Kafelki w obszarze roboczym zarządzania wynagrodzeniami nie będą działać poprawnie, jeśli użyjesz tej funkcji.
- W formularzu **pracownika** karta **Lista płac**, grupa **Gotowe do zapłaty** jest dostępna dla każdej roli użytkownika. 

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
