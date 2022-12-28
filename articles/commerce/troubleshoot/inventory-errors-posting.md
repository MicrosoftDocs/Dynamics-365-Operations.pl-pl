---
title: Błędy księgowania zestawienia z powodu niedostępnych zapasów lub konfliktów aktualizacji
description: Ten artykuł przedstawia możliwe rozwiązania problemów związanych z inwentaryzacją podczas księgowania zestawień w Microsoft Dynamics 365 Commerce.
author: Shajain
ms.date: 12/19/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: cebb890b42def6e9b002b01be63266b88bfc35a4
ms.sourcegitcommit: 4ad87483ba0bfea3e04fdb7e578d8abc34e607a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2022
ms.locfileid: "9887633"
---
# <a name="statement-posting-errors-due-to-unavailable-inventory-or-update-conflicts"></a>Błędy księgowania zestawienia z powodu niedostępnych zapasów lub konfliktów aktualizacji

[!include [banner](../../includes/banner.md)]

Ten artykuł przedstawia możliwe rozwiązania problemów związanych z inwentaryzacją podczas księgowania zestawień w Microsoft Dynamics 365 Commerce.

## <a name="description"></a>opis

W trakcie księgowania transakcji handlowych możesz otrzymywać komunikaty o błędach związanych z problemami z zasobami lub konfliktami aktualizacji.

### <a name="inventory-issues-error-message"></a>Komunikat o błędzie problemów z zapasami

Jeśli napotkasz problemy z zapasami, komunikat o błędzie, który otrzymasz, będzie przypominał ten przykład:

> xx nie może zostać wybrany, ponieważ tylko yy jest/jest dostępny w magazynie

### <a name="update-conflict-error-messages"></a>Komunikaty o błędach związanych z konfliktem aktualizacji

Problem konfliktu aktualizacji może wystąpić, gdy metodą wyceny zapasów jest *koszt standardowy* lub *średnia krocząca*. Ponieważ obie te metody są metodami kalkulacji kosztów wieczystych, ostateczny koszt jest ustalany w momencie księgowania.

Jeśli używasz metody *średniej ruchomej*, komunikat o błędzie konfliktu aktualizacji, który otrzymasz, będzie przypominał ten przykład:

> Wartość zapasów xx,xx nie jest oczekiwana po obliczeniu proporcjonalnych wydatków

Jeśli używasz metody *koszt standardowy*, komunikat o błędzie konfliktu aktualizacji, który otrzymasz, będzie przypominał ten przykład:

> Koszt standardowy jest niezgodny z wartością zapasów finansowych po aktualizacji. Wartość = xx,xx, ilość = yy,yy, koszt standardowy = zz,zz

## <a name="resolutions"></a>Rozwiązania

### <a name="workaround-for-the-inventory-error"></a>Obejście dla błędu inwentaryzacji

Błąd w stanie magazynowym można zniwelować poprzez ręczną aktualizację stanu magazynowego dla danego artykułu lub poprzez włączenie fizycznej inwentaryzacji ujemnej dla grupy modelu artykułu, która jest powiązana z tym artykułem w Commerce headquarters.

Aby zapewnić spójność księgowania, firma Microsoft zaleca włączenie ujemnej inwentaryzacji fizycznej dla grupy modelu elementu. W niektórych scenariuszach księgowanie zestawień może być niemożliwe, jeśli nie zostanie włączona opcja ujemnego spisu zapasów fizycznych.

Na przykład dany przedmiot nie jest dostępny w magazynie, ale kasjer zwraca go, a następnie dodaje do tej samej transakcji po obniżonej cenie, aby naśladować dopasowanie cen. W tym przypadku zarówno transakcja zwrotu, jak i transakcja sprzedaży zostaną wciągnięte do tego samego zestawienia pojedynczego zamówienia klienta. Ponieważ jednak nie ma gwarancji, że wiersz zwrotu (który zwiększa stan zapasów) zostanie zaksięgowany przed wierszem sprzedaży (który zmniejsza stan zapasów), mogą pojawić się błędy w stanie zapasów. Jeśli w tym scenariuszu włączona jest fizyczna inwentaryzacja negatywna, nie ma to wpływu na księgowanie transakcji, a system prawidłowo odzwierciedla inwentaryzację.

#### <a name="enable-negative-physical-inventory-for-an-item-model-group"></a>Włączenie ujemnego stanu zapasów fizycznych dla grupy modeli obiektów

Aby włączyć negatywny spis zapasów fizycznych dla grupy modeli przedmiotów w Commerce headquarters, wykonaj poniższe kroki.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Magazyn**.
1. W lewym okienku nawigacyjnym zaznacz grupę modeli przedmiotów.
1. W sekcji **Zasady zapasów**, w zakładce **Ujemne zapasy** zaznacz pole wyboru **Fizyczne ujemne zapasy**.

![Fizyczne zapasy ujemne – włączono.](./media/Physical_Negative_Inventory.png)

### <a name="workaround-for-the-update-conflict-error"></a>Obejście błędu konfliktu aktualizacji

Możliwe sposoby naprawienia błędu związanego z konfliktem aktualizacji znajdziesz w sekcji [Konflikt aktualizacji pojawia się, gdy metodą wyceny zapasów jest koszt standardowy lub średnia krocząca.](/troubleshoot/dynamics-365/supply-chain/costing/update-conflict-standard-cost-moving-average-inventory-valuation).

> [!NOTE]
> W przypadku błędu konfliktu aktualizacji nie musisz usuwać zamówień klientów, które zostały wygenerowane przy użyciu kroku agregacji księgowania. Po zastosowaniu sugerowanych rozwiązań oświadczenie powinno zostać wysłane przy ponownej próbie wysłania oświadczenia.
