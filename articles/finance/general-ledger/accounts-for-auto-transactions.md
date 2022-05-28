---
title: Konta dla transakcji automatycznych
description: W tym temacie wyjaśniono, w jaki sposób konta dla transakcji automatycznych są używane do księgowania za pośrednictwem Microsoft Dynamics 365 i przedstawiono przykłady kont kluczowych dla transakcji automatycznych.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 275c74d673d1ba2468e23c5fa443c9272d13a184
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735268"
---
# <a name="accounts-for-automatic-transactions"></a>Konta dla transakcji automatycznych

Na stronie **Konta transakcji automatycznych** (**Księga główna &gt; Ustawienia księgowania &gt; Konta dla transakcji automatycznych**) służy do definiowania domyślnego konta głównego, które jest używane dla każdego typu księgowania w systemie . Chociaż większość typów księgowania można skonfigurować na stronie specyficznej dla modułu lub funkcji, niektóre typy księgowania można skonfigurować tylko na stronie **Konta dla transakcji automatycznych**.

Możesz na przykład określić główne konto używane dla typu księgowania **Saldo klientów** w polu **Podsumowanie** na stronie **Profil księgowania klienta** i użyć innego konta głównego do każdy profil klienta. W ten sposób można uzyskać bardziej szczegółową kontrolę księgować. Z drugiej strony konto błędu można określić tylko na stronie **Konta dla transakcji automatycznych**.

Po otwarciu strony **Konta dla transakcji automatycznych** w nowej firmie lista kont będzie pusta. Możesz dodać najpopularniejsze typy publikowania, które należy skonfigurować na stronie, wybierając przycisk **Utwórz typy domyślne**. Następnie dla każdego wiersza możesz wybrać konto główne w polu **Konto główne**. Jeśli pole **Konto główne** pozostawisz puste dla danego typu księgowania, a nie skonfigurowano konta głównego na stronie specyficznej dla modułu lub funkcji, podczas księgowania transakcji korzystającej z tego typu księgowania pojawi się komunikat o błędzie. Zazwyczaj komunikat będzie mieć treść „Nie można odnaleźć konta dla \[typu księgowania\]”.

## <a name="default-posting-types"></a>Domyślne typy księgowania

W poniższej tabeli przedstawiono przykłady domyślnych typów księgowania, które są tworzone po wybraniu opcji **Utwórz typy domyślne** na stronie **Konta dla transakcji automatycznych**. Pokazuje przykładowe konta główne i opisy. „Uznanie/kredyt?” kolumna „Ma” wskazuje, czy transakcja zwykle księguje debet czy kredyt. W niektórych przypadkach transakcja może księguje debet lub kredyt. Kolumna „Konto rozliczeniowe” wskazuje typ księgowania jako konto rozliczeniowe. Jeżeli typem księgowania jest konto rozliczeniowe, kwota księgowana na koncie jest automatycznie stornowana po zaksięgowaniu późniejszej transakcji.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Różnica groszowa w walucie raportowania | 618160 | Inne wydatki | Wydatek | Obie | Nie | Ten typ księgowania jest używany, gdy występuje różnica groszowa, gdy kwota transakcji w walucie obcej jest przeliczana na walutę raportowania. |
| Różnica groszowa w walucie rozliczeniowej | 618160 | Inne wydatki | Wydatek | Obie | Nie | Ten typ księgowania jest używany, gdy występuje różnica groszowa, gdy kwota transakcji w walucie obcej jest przeliczana na walutę księgowania. |
| Konto błędu | 999999 | Konto błędu | Wydatek | Obie | Nie | Ten typ księgowania jest używany w przypadku wystąpienia błędu w systemie. Poprawność konta powinna być sprawdzana w każdym okresie, a wszelkie błędy powinny zostać rozwiązane. |
| Wynik na koniec roku | 300160 | Wstrzymane dochody | Kapitał własny | Obie | Nie | Ten typ księgowania jest używany, gdy uruchamiany jest proces zamknięcia na koniec roku w celu przeniesienia salda kont typu **Zysk i strata** na konto główne wybrane dla wyniku na koniec roku. |
| Rabat gotówkowy odbiorcy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie | Typ księgowania zdefiniowany na stronie **Konta dla transakcji automatycznych** nie jest używany. Konto główne jest wymagane, gdy rabaty gotówkowe są skonfigurowane w rozrachunkach z odbiorcami.|
| Rabat gotówkowy dostawcy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie dotyczy | Nie | Typ księgowania zdefiniowany na stronie **Konta dla transakcji automatycznych** nie jest używany. Konto główne jest wymagane, gdy rabaty gotówkowe są skonfigurowane w rozrachunkach z dostawcami. |

## <a name="additional-posting-types"></a>Dodatkowe typy księgowania

W poniższej tabeli przedstawiono przykłady dodatkowych typów księgowania, które należy skonfigurować, jeśli planujesz korzystać z powiązanych funkcji. Dla tych typów księgowania konfiguracja profilu księgowania nie jest dostępna w innym module. „Uznanie/kredyt?” kolumna „Ma” wskazuje, czy transakcja zwykle księguje debet czy kredyt. W niektórych przypadkach transakcja może księguje debet lub kredyt. Kolumna „Konto rozliczeniowe” wskazuje typ księgowania jako konto rozliczeniowe. Jeżeli typem księgowania jest konto rozliczeniowe, kwota księgowana na koncie jest automatycznie stornowana po zaksięgowaniu późniejszej transakcji.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Konto bilansowe dla różnic konsolidacji | 801200 | Zysk i strata — przesliowanie | Wydatek | Obie | Nie | Ten typ księgowania jest używany podczas konsolidacji obejmującej przeszacowanie waluty, a podczas przeszacowania występują różnice groszowe. |
| Konto wynikowe dla różnic konsolidacji  | 801200 | Zysk i strata — przesliowanie | Wydatek | Obie | Nie | Ten typ księgowania jest używany podczas konsolidacji obejmującej przeszacowanie waluty, a podczas przeszacowania występują różnice groszowe. |
| Międzyjednostkowe – debet | 133500 | Należności międzyjednostce | Element zawartości | Uznanie | Nie | Ten typ księgowania jest używany po wybraniu wymiaru bilansowania na stronie **Księga**, a wymiar nie bilansuje się w zaksięgowanej transakcji. |
| Międzyjednostkowe — kredyt | 233500 | Zobowiązania międzyjednostowe | Pasywa | Środki | Nie | Ten typ księgowania jest używany po wybraniu wymiaru bilansowania na stronie **Księga**, a wymiar nie bilansuje się w zaksięgowanej transakcji. |
