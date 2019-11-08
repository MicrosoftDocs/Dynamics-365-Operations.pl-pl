---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (11 stycznia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4bf106507800f53be80af1733667bfec3023b56f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551848"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (11 stycznia 2019 r.)

[!include [banner](includes/banner.md)]

**Kompilacja 8.1.2100**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="changes"></a>Zmiany

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Sprawdzenie poprawności wniosków urlopowych poprzez prognozowanie dostępnego salda
Zmiany wprowadzone w tej wersji pozwalają pracownikom złożyć wniosek o przyszły urlop bez odejmowania czasu z bieżącego salda. Standardowe przepływy pracy będą używane dla wszelkich wniosków wprowadzonych w przyszłości. Aby uzyskać więcej informacji, zobacz [Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin](leave-accrue-hours-worked.md).

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Wyświetlanie prognozowanego salda urlopu w obszarach roboczych „Portal pracowników” i „Osoby”
Ta funkcja umożliwia przeglądanie salda przyszłych okresów urlopowych przez pracowników HR, kadrę kierowniczą i pracowników. Pracownicy mogą wyświetlać przyszłe salda w obszarze roboczym **Portal pracowników**, a pracownicy HR mają dostęp tych samych informacji w przestrzeni roboczej **Osoby**.

### <a name="notifications-for-changing-leave-balances"></a>Powiadomienia o zmianach sald urlopowych
Salda urlopowe będą wyświetlały bieżące saldo pracownika. Salda przyszłe można wyświetlić w obszarach roboczych **Portal pracowników** i **Osoby**, otwierając widok „na dzień” w celu obliczenia prognozowanego salda.

Dodano opcje nawigacji, aby umożliwić wyświetlanie prognozowanych sald w następujących obszarach:
  - Karta **Czas wolny** w obszarze roboczym **Portal pracowników**.
  - Karta **Urlopy i nieobecności** w obszarze roboczym **Samoobsługa menedżera**.
  - Strona **Urlopy i nieobecności** w obszarze roboczym **Osoby**

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Zezwalanie na miejsca dziesiętne dla planów wynagrodzeń o zmiennej wysokości (systemów gotówkowych)
Zmienne nagród w postaci wypłat gotówkowych i plany zapewniają teraz dodatkową elastyczność dla kwot i zastąpień dla wartości z wartościami dziesiętnymi.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>Nie można zmienić dat zapisów wynagrodzeń o zmiennej wysokości po zapisaniu planu
Ta zmiana pozwala na aktualizowanie daty zakończenia planu (przedłużenie lub wygaśnięcie) po zapisaniu planu. Nadal można włączyć lub ponownie aktywować plan niezależnie od dat rozpoczęcia i zakończenia.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>Informacja o liście płac dostępna po przypisaniu roli zabezpieczeń administratora listy płac
Roli administratora listy płac została zaktualizowana i ma teraz dostęp do informacji o liście płac podczas procesu żądania.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Portal pracowników | Wyświetlanie hierarchii stanowisk z kafelka nie wyświetla węzła nadrzędnego
Wprowadzono zmiany w celu wyeliminowania błędu, który występował podczas dodawania hierarchii stanowisk do nowych obszarów roboczych i poruszanie się w obrębie struktury organizacyjnej.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Nowy komunikat sprawdzania poprawności, kiedy sekwencja numerów pracownika jest używana
Wprowadzono zmianę celem objaśnienia, na czym polega problem gdy zatrudniasz pracownika, a następny numer pracownika jest zajęty.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>Obszar roboczy samoobsługi pracownika wybrany jako początkowa strona startowa
Gdy obszar roboczy **Samoobsługa pracownika etatowego** jest wybrany jako początkowa strona startowa dla użytkownika i użytkownik nie ma przypisanej roli pracownika, system przekieruje do domyślnego pulpitu.

### <a name="termination-reason-code-updates-position-assignment-record"></a>Kod przyczyny zakończenia zatrudnienia aktualizuje rekord przypisania stanowiska
Kod przyczyny zakończenia zatrudnienia teraz aktualizuje przypisanie stanowiska w przypadku zakończenia stosunku pracy z pracownikiem i wyłączenia stanowiska. 
